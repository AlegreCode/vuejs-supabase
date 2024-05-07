<script setup>
import { onMounted, ref } from 'vue'
import BoxImage from './BoxImage.vue'
import { supabase } from '../supabase/supabase';

const arrayImages = ref([]);

const channels = supabase.channel('custom-insert-channel')
  .on(
    'postgres_changes',
    { event: 'INSERT', schema: 'public', table: 'images' },
    (payload) => {
      arrayImages.value.push(payload.new);
    }
  )
  .subscribe()

onMounted(async() => {  
  let { data } = await supabase.from('images').select('*');
  arrayImages.value = data;  
          
})
</script>
<template>
    <div class="col-9">
        <h2 class="display-5 text-center p-3">Galería</h2>
        <hr>
        <div class="grid-container">
            <BoxImage v-for="img in arrayImages" :key="img.id" :img="img"/>
        </div>
    </div>
</template>
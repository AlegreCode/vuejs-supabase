<script setup>
import { ref } from 'vue';
import { supabase } from '../supabase/supabase';


const title = ref('')
const fileInput = ref('')

async function handleSubmit() {
  const file = fileInput.value.files[0];
  const { data } = await supabase.storage.from('gallery').upload(file.name, file);
  console.log(data);
  const { data: publicUrl } = await supabase.storage.from('gallery').getPublicUrl(file.name);
  console.log(publicUrl);
  document.querySelector('#preview').src = "https://fakeimg.pl/200x200/?text=IMG";
  title.value = "";
}

function handleFileChange(event) {
  var file = event.target.files[0];
  var url = URL.createObjectURL(file);
  document.querySelector('#preview').src = url;
};
</script>

<template>
    <div class="col-3">
        <div class="card">
          <div class="card-body">
            <h2 class="display-5 text-center">Subir Imagen</h2>
            <form @submit.prevent="handleSubmit">
              <div class="form-group mb-3 text-center">
                <img src="https://fakeimg.pl/200x200/?text=IMG" alt="vista previa" id="preview" class="img-thumbnail">
              </div>
              <div class="form-group mb-3">
                <label for="formFile" class="form-label">Imágen</label>
                <input class="form-control" type="file" id="formFile" @change="handleFileChange" ref="fileInput">
              </div>
              <div class="form-group mb-3">
                <label for="title">Título</label>
                <input type="text" class="form-control" id="title" v-model="title">
              </div>
              <div class="form-group d-grid">
                <button type="submit" class="btn btn-primary">Subir</button>
              </div>
            </form>
          </div>
        </div>
      </div>
</template>
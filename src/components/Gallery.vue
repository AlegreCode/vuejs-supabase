<script setup>
import { ref } from 'vue'
import BoxImage from './BoxImage.vue'

const data = ref([
  {
    "title": "image1",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image2",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image3",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image4",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image5",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image6",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image7",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image8",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image9",
    "url": "https://picsum.photos/600/300"
  },
  {
    "title": "image10",
    "url": "https://picsum.photos/600/300"
  }
])
</script>
<template>
    <div class="col-9">
        <h2 class="display-5 text-center p-3">Galería</h2>
        <hr>
        <div class="grid-container">
            <template v-for="img in data">
                <BoxImage :img="img"/>
            </template>
        </div>
    </div>
</template>
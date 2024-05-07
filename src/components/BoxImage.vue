<script setup>

const { img } = defineProps({img: { type: Object, required: true}});
</script>
<template>
    <figure class="box-image">
        <img :src="img.url_image" class="image">
        <figcaption class="title-image d-flex justify-content-center align-items-center display-5">{{img.title}}</figcaption>
    </figure>
</template>
<script setup>
const { img } = defineProps(['img'])
</script>
<template>
    <figure class="box-image">
        <img :src="img.url" class="image">
        <figcaption class="title-image d-flex justify-content-center align-items-center display-5">{{img.title}}</figcaption>
    </figure>
</template>
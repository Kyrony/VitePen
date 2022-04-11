<script>

export default {
  props: {
    picture: {
          type: String,
          required: true
    },
    caption: String,
  },
}

</script>

<template>

    <figure>
    <img :src=picture>
    <figcaption>{{ caption }}</figcaption>
    </figure>

</template>

<style scoped>

figure img {
    width: 100%;
}

</style>
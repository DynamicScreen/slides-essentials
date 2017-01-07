<template>
  <div>
    <h2 class="slide-title" :style="{ color: '#' + slide.color }">
      <i class="fa" :class="[slide.icon]"></i>
      {{ slide.data.title }}
    </h2>
    <div class="center">
      <div class="image-container" :style="{ backgroundImage: 'url(\'' + slide.data.url + '\')' }"></div>
      <p class="caption">{{ slide.data.description }}</p>
    </div>
  </div>
</template>
<style scoped>
  .center {
    text-align: center;
  }

  img {
    width: auto;
  }

  .caption {
    font-size: 2em;
  }

  .image-container {
    height: 50vh;
    width: 100%;
    background: no-repeat center top;
    -webkit-background-size: contain;
    background-size: contain;
  }
</style>
<script>
  export default {
    props: ['slide']
  }
</script>

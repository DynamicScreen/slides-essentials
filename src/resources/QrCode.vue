<template>
  <div>
    <h2 class="slide-title" :style="{ color: '#' + slide.color }">
      <i class="fa" :class="[slide.icon]"></i>
      {{ slide.data.title }}
    </h2>
    <div class="center">
      <div class="image-container">
        <img :src="qrCodeUrl">
      </div>
      <p>{{ slide.data.description }}</p>
    </div>
  </div>
</template>

<style scoped>
  .center {
    text-align: center;
  }

  .image-container {
    display: inline-block;
    height: 50vh;
    overflow: hidden;
  }

  img {
    transform: scale(1.25);
    height: 100%;
  }
</style>

<script>
  export default {
    computed: {
      qrCodeUrl () {
        return 'https://chart.googleapis.com/chart?cht=qr&chs=400x400&chl=' + this.slide.data.url
      }
    },
    props: ['slide']
  }
</script>

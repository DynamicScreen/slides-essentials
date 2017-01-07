<template>
    <div>
        <h2 class="slide-title" :style="{ color: '#' + slide.color }">
            <i class="fa" :class="[slide.icon]"></i>
            {{ slide.data.title }}
        </h2>
        <div class="message-text">{{ slide.data.message }}</div>
    </div>
</template>
<style scoped>
    .message-text {
        font-size: 4.5em;
        text-align: center;
        margin-top: 1vh;
        height: 60vh;
    }
</style>
<script>
  export default {
    props: ['slide']
  }
</script>

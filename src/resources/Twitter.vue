<template>
  <div>
    <h2 class="slide-title" :style="{ color: '#' + slide.color }">
      <i :class="'fa ' + slide.icon"></i>
      {{ slide.data.title }}
    </h2>
    <div class="row">
      <div class="tweet col-sm-1-2" v-for="tweet in slide.data.tweets">
        <md-card>
          <md-card-header>
            <div class="md-title">
              <img :src="tweet.avatar" :alt="tweet.name">
              @{{ tweet.name }}
            </div>
          </md-card-header>
          <md-card-content>
            <div :class="{'row': tweet.media_url}">
              <div class="col-5-12 tweet-image" v-if="tweet.media_url">
                <img :src="tweet.media_url">
              </div>
              <div :class="{'col-7-12': tweet.media_url}" v-html="tweet.formatted_text"></div>
            </div>
          </md-card-content>
        </md-card>
      </div>
    </div>
  </div>
</template>
<style scoped>
  .md-title img {
    max-width: 1.5em;
    max-height: 1.5em;
    vertical-align: middle;
    border-radius: 50%;
  }

  .tweet {
    padding: 0.8em;
    font-size: 0.7em;
  }

  .tweet-image {
    padding-right: 3%;
  }

  .tweet .md-card-content {
    font-size: 1em;
  }

  .md-title {
    color: #4099FF;
  }
</style>
<style>
  .tweet .highlight {
    color: #4099FF;
  }
</style>
<script>
  export default {
    props: ['slide']
  }
</script>

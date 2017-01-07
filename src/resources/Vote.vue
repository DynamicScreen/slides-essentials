<template>
  <div>
    <h2 class="slide-title" :style="{ color: '#' + slide.color }">
      <i class="fa" :class="[slide.icon]"></i>
      {{ slide.data.title }}
    </h2>
    <h3 class="question">
      {{ slide.data.description }}
    </h3>
    <template v-if="slide.data.ended">
      <div class="answers">
        <md-whiteframe md-elevation="3" class="answer" :class="{ winner: answer.winner }"
                       v-for="answer in slide.data.answers">
          <div class="right stats"><strong>{{ answer.votes }}</strong> votes ({{ answer.percentage }}%)</div>
          {{ answer.text }}
        </md-whiteframe>
      </div>
    </template>
    <template v-else>
      <div class="tip">
        Répondez sur <span class="twitter"><span class="fa fa-twitter"></span> Twitter</span>
      </div>
      <div class="answers">
        <md-whiteframe md-elevation="3" class="answer" v-for="answer in slide.data.answers">
          <div class="right">avec <strong :style="{ color: '#' + slide.color }">{{ answer.hashtag }}</strong></div>
          {{ answer.text }}
        </md-whiteframe>
      </div>
    </template>
  </div>
</template>

<style scoped>
  .tip {
    text-align: right;
    font-weight: 300;
  }

  .answer {
    padding: 1em 1em;
    margin-top: 0.5em;
  }

  .right {
    float: right;
  }

  .twitter {
    color: #4099FF;
    font-weight: 500;
  }

  .stats {
    font-weight: 300;
    color: #388E3C;
  }

  .winner {
    background-color: #E8F5E9;
  }
</style>

<script>
  export default {
    props: ['slide']
  }
</script>

<template>
  <div class="score">
      <p>Reaction Time: {{ score }} ms</p>
      <p class="rank">{{ rank }}</p>
  </div>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
        if(this.score < 250) {
            this.rank = '😲Flash or What'
        }
        else if(this.score < 400) {
            this.rank = '😮Rapid Reflexes'
        }
        else {
            this.rank = '😢Snail pace....'
        }
    }
}
</script>

<style>
    .score > p {
        font-style: italic;
        font-weight: bold;
        font-size: 1.2em;
    }

    .rank {
        font-size: 1.8em;
        color: #0faf87;
        font-weight: bold;
    }
</style>
<template>
  <div>
    <h1>Bingo Card</h1>
    <div class="bingo-card">
      <BingoSquare v-for="(item, index) in items" :key="index" :msg="item"/>
    </div>
  </div>
</template>

<script>
import BingoSquare from './BingoSquare.vue';

export default {
  name: 'BingoCard',
  props: {
    items: Array,
  },
  components: {
    BingoSquare,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bingo-card {
  max-width: 75%;
  margin: 0 auto;
  display: grid;
  grid-template-rows: 1fr 1fr 1fr 1fr 1fr 1fr;
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
}
</style>

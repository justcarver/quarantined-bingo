<template>
  <div class="square" @click="clickSquare">
    <p>{{ msg }}</p>
    <div v-if="clicked || autoClicked" class="selected"></div>
  </div>
</template>

<script>
export default {
  name: 'BingoSquare',
  props: {
    msg: String,
  },
  data() {
    return {
      clicked: false,
    };
  },
  methods: {
    clickSquare() {
      if (this.clickable) {
        this.clicked = !this.clicked;
      }
    },
  },
  computed: {
    clickable() {
      if (this.msg.length === 1 || this.msg === 'FREE!') {
        return false;
      }
      return true;
    },
    autoClicked() {
      if (this.msg === 'FREE!') {
        return true;
      }
      return false;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.square {
  position: relative;
  text-align: center;
  border: 1px black solid;
  min-height: 50px;
  min-width: 50px;
  padding: 5px;
}

.selected {
  z-index:-1;
  background-color: rgba(0, 200, 0, .5);
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border-radius: 100%;
}
</style>

<template>
  <div id="app">
    <button v-on:click="changeState">Block on/off</button>
    <Block :is-show-block="stateIsShow" />
    {{stateIsShow}}
  </div>
</template>

<script>
import Block from './components/Block'
export default {
  components: {
    Block
  },
  data() {
    return {
        stateIsShow: false
    }
  },
  methods:{
    changeState() {
      this.stateIsShow = !this.stateIsShow
    },
  }
}
</script>

<style scoped>
  h2 {
    color: red;
  }
</style>

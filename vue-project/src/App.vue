<template>
  <div id="app">
    <button v-on:click="changeState" class="button">Block on/off</button>
    <Block :is-show-block="stateIsShow" @update:state="handlerState" />
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
        stateIsShow: true
    }
  },
  methods:{
    changeState() {
      this.stateIsShow = !this.stateIsShow;
    },
    handlerState() {
      this.stateIsShow = false;
    }
  }
}
</script>

<style scoped>
  h2 {
    color: red;
  }
</style>

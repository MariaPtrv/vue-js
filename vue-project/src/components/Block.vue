<template>
    <div class="block" :class="{hide: !isShow}">
      hello {{isShow}}
    </div>
</template>

<script>
export default {
  name: "Block",
  data() {
    return {
      isShow: true
    }
  },
  mounted() {
    document.addEventListener('click', this.onClick)
  },
  beforeUnmount()  {
    document.removeEventListener('click', this.onClick);
  },
  props:{
    isShowBlock:{
      type: Boolean,
      default: true
    }
  },
  watch: {
    isShowBlock() {
      console.log(this.isShowBlock);
      this.isShow = this.isShowBlock;
    }
  },
  methods:{
    onClick({target}){
      if (!target.closest('.block') && this.isShow) {
        //.isShow = false
      }
    }
  }
}
</script>

<style scoped>
.block{
  height: 50px;
  width: 50px;
  background: crimson;
  visibility: visible;
}

.hide{
  visibility: hidden;
}
</style>

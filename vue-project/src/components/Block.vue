<template>
    <div class="block" :class="{hide: !isShowBlock}">
      hello {{isShowBlock}}
    </div>
</template>

<script>
export default {
  name: "Block",
  props:{
    isShowBlock: {
      type: Boolean,
      default: true
    }
  },
  emits: ['update:state'],
  mounted() {
    document.addEventListener('click', this.onClick)
  },
  beforeUnmount()  {
    document.removeEventListener('click', this.onClick);
  },
  methods:{
    onClick({target}){
      if (!target.closest('.block') && this.isShowBlock && !target.closest('.button')) {
        this.$emit('update:state');
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

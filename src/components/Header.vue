<template lang="html">
  <div class="headerview">
      <h1>{{msg}}</h1>      
  </div>

</template>

<script>
export default {
  data () {
    return {
      title: '我是標題部分...'
    }
  },
  // 第一步: props
  props: {
    msg: { // 自定義指令
      type: String,
      default: '我是誰啊?'
    }
  }
}
</script>

<style lang="css" scoped>
</style>

<template>
  <div class="demo">
    <div class="color-test">
      <span class="dark">主色(深色)</span>
      <span class="light">浅色</span>
      <span class="gray">灰色(主色灰)</span>
      <span class="blue">蓝色</span>
      <span class="red">红色</span>
      <span class="orange">橘色</span>
      <span class="green">绿色</span>
      <span class="grey">灰色(边框灰)</span>
      <span class="white">白色</span>
    </div>
    <g-button>瓜坤的按钮</g-button>
    <g-icon name="loading"></g-icon>
  </div>
</template>

<script>
  import GButton from './button'
  import GIcon from './icon'

  export default {
    name: "Demo",
    components: {
      GButton, GIcon
    }
  }
</script>

<style scoped>

</style>

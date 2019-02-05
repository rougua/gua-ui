<template>
  <svg class="gua-icon">
    <use :xlink:href="`#icon-${name}`"></use>
  </svg>
</template>

<script>
  export default {
    name: "GuaIcon",
    props: {
      name: {}
    }
  }
</script>

<style scoped lang="scss">
  .gua-icon {
    width: 1em; height: 1em;
  }
</style>

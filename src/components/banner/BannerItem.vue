<template>
  <li
    v-if="banner"
    class="banner-item"
  >
    <a
      :href="banner.url"
      class="b-link"
      target="_blank"
    >
      <img :src="banner.pic">
    </a>
  </li>
</template>
<script>
export default {
  props: {
    banner: {
      type: Object,
      default: () => {}
    }
  }
}
</script>

<style lang="stylus" scoped>
.banner-item
  width 440px
  height 220px
  float left
  overflow hidden
  .b-link
    color #fff
    width 100%
    height 100%
    img
      width 100%
      height 100%
</style>

<template>
  <div class="content">
    <div class="container-top-wrapper">
      <div class="container-top">
        <div class="b-l">
          <Banner />
        </div>
        <div class="b-r">
          <BContentTop />
        </div>
      </div>
    </div>
    <!-- 推广 -->
    <div class="container-row">
      <BPromote />
    </div>
    <!-- 直播 -->
    <div class="container-row">
      <BLive />
    </div>
    <!-- 各分类具体内容 -->
    <div
      v-for="(row, index) in rows"
      :id="row.b_id"
      :key="index"
      class="container-row"
    >
      <BContentRow
        v-if="rows"
        :category="row.category"
        :category-id="row.categoryId"
        :row="row.item"
      />
    </div>
  </div>
</template>

<script>
import Banner from 'components/banner/Banner'
import BContentTop from 'components/contentTop/BContentTop'
import BPromote from 'components/promote/BPromote'
import BLive from 'components/live/BLive'
import BContentRow from 'components/contentRow/BContentRow'

export default {
  components: {
    Banner,
    BContentTop,
    BPromote,
    BLive,
    BContentRow
  },
  props: {
    rows: {
      type: Array
    }
  }
}
</script>

<style lang="stylus" scoped>
.content
  zoom 1
  .container-top-wrapper
    &:after
      content ''
      display block
      visibility hidden
      height 0
      clear both
      font-size 0
  .container-top
    padding 0
    margin 0 auto
    margin-bottom 20px
    zoom 1
    width 980px
    &:after
      content ''
      display block
      visibility hidden
      height 0
      clear both
      font-size 0
    .b-l
      float left
      width 440px
    .b-r
      float right
      width 540px
      height auto
  .container-row
    margin 0 auto
    zoom 1
    width 980px
    &:after
      content ''
      display block
      visibility hidden
      height 0
      clear both
      font-size 0
</style>

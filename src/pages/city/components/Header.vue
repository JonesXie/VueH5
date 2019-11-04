<template>
  <div class="header">
    选择城市
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>

</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .header
    position relative
    height $headerHigh
    line-height $headerHigh
    text-align center
    background-color $bgColor
    color #fff
    font-size .32rem
    overflow hidden
    .header-back
      position absolute
      top 0
      left 0
      width .64rem
      text-align center
      font-size .4rem
      color #fff
</style>

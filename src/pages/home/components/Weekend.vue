<template>
  <div>
    <div class="title">周末去哪玩</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wraper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .title
    line-height : .8rem
    text-indent : .2rem
    background : #eee
  .item-img-wraper
    overflow: hidden
    width : 100%
    height : 0
    padding-bottom : 38%
    .item-img
      width : 100%
  .item-info
    padding: .1rem
    text-indent : .15rem
    .item-title
      line-height : .54rem
      font-size : .32rem
      ellipsis()
    .item-desc
      line-height : .4rem
      color : #ccc
      ellipsis()
</style>

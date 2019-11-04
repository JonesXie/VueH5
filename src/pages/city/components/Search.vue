<template>
  <div>
    <div class="search">
      <input type="text" v-model="keyword" class="search-input" placeholder="请输入城市名或拼音">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li v-for="item of list" class="search-item border-bottom" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">
          没有找到匹配数据
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'

export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('./')
      this.keyword = ''
    },
    ...mapMutations(['changeCity'])
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search, {
      click: true,
      taps: true
    })
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .search
    height 0.72rem
    background-color $bgColor
    padding 0 0.2rem
    .search-input
      text-align center
      height .62rem
      line-height .62rem
      width 100%
      box-sizing border-box
      padding 0 .1rem
      text-align center
      border-radius 0.06rem
      color #666
  .search-content
    overflow hidden
    width 100%
    position absolute
    top 1.58rem
    left 0
    bottom 0
    background-color #eee
    z-index 1
    .search-item
      line-height .62rem
      padding-left .2rem
      background-color #fff
      color #666
</style>

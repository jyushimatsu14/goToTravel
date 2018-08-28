<template>
  <div class="header" ref="wrapper">
    <div>
      <router-link to="/">
        <div class="iconfont header-back">&#xe624;</div>
      </router-link>
      城市选择
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'CityHeader',
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    overflow:hidden
    height:$headerHeight
    line-height:$headerHeight
    text-align:center
    color:#fff
    background-color:#f5f5f5
    background:$bgColor
    font-size:.32rem
    .header-back
      position:absolute
      top:0
      left:0
      width:.64rem
      text-align:center
      font-size:.4rem
      color:#fff
</style>

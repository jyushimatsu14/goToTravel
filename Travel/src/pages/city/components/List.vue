<template>
  <div class="list" ref="wrapper">
    <div>
        <h2 class="title hot-city">热门城市</h2>
        <ul class="button-list">
          <li class="button-wrapper"
              v-for="item of hot"
              :key="item.id"
              @click="hanldeCityClick(item.name)"
          >
            {{item.name}}
          </li>
        </ul>
        <div>
          <h2 class="title">字母排序</h2>
          <ul class="letter-list">
            <li class="letter-wrapper"
                v-for="(item,key) of cities"
                :key="key"
            >
              <a class="link-wrapper" :href="'#'+key">
                {{key}}
              </a>
            </li>
          </ul>
          <div
            v-for="(item,key) of cities"
            :key="key"
          >
            <a :id="key"></a>
            <h2 class="title" >{{key}}</h2>
            <ul class="button-list attress-list">
              <li
                class="attress-wrapper"
                v-for="innerItem of item"
                :key="innerItem.id"
                @click="hanldeCityClick(innerItem.name)"
              >
                {{innerItem.name}}
              </li>
            </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object
  },
  methods: {
    hanldeCityClick (city) {
      // this.$store.commit('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    background: #f5f5f5
    font-size: .28rem
    height:999
    .title
      font-size:.24rem
      margin:.24rem .3rem
    .hot-city
      margin-top:0
      padding-top:.24rem
    .button-list
      position: relative
      display:block
      overflow: hidden
      z-index: 0
      list-style: none
      background-color:#fff
      &:before
        content: '';
        position: absolute;
        width: 33.33%;
        left: 33.33%;
        height: 100%;
        border-left: .02rem solid #ddd;
        border-right: .02rem solid #ddd;
      .button-wrapper
        position: relative
        float: left
        z-index: 10
        width:33.33%
        height: .9rem
        line-height: .9rem
        font-size: .28rem
        text-align: center
        border-bottom: .02rem solid #ddd
        margin-bottom: -1px
    .letter-list
      position: relative
      overflow: hidden
      z-index: 0
      padding: .3rem 0
      background-color:#fff
      .letter-wrapper
        position: relative
        float: left
        z-index: 10
        width: 16.66%
        height: .9rem
        line-height: .9rem
        font-size: .28rem
        text-align: center
        color: #212121
        .link-wrapper
          display: block
          overflow: hidden
          font-size: .28rem
          color: #212121
    .attress-list
      &:before
        content: ''
        position: absolute
        width: 25%
        left: 25%
        height: 100%
        border-left: .02rem solid #ddd
        border-right: .02rem solid #ddd
      &:after
        content: ''
        position: absolute
        width: 10%
        left: 75%
        height: 100%
        border-left: .02rem solid #ddd
        border-right: 0
      .attress-wrapper
        float: left
        position: relative
        z-index: 10
        width: 25%
        height: .9rem
        line-height: .9rem
        font-size: .28rem
        text-align: center
        border-bottom: .02rem solid #ddd
        margin-bottom: -1px
        color: #212121
</style>

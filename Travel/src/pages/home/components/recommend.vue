<template>
  <div>
    <div class="group-title">
      <img class="title-img"
           src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" alt="本周热门榜单">
      <span class="title">本周热门榜单</span>
      <a class="more-title"
         href="#">全部榜单
         <span class="iconfont"> > </span>
      </a>
    </div>
    <ul class="hotsale-list">
      <li class="hotsale-item"
          v-for="item of recommendList"
          :key="item.id">
        <div class="hotsale-imgcon">
          <img class="imgcon" :src="item.imgUrl">
        </div>
        <div class="hotsale-sight">
          {{item.title}}
        </div>
        <div class="hotsale-price">
          <span class="price">￥
            <em class="price-num">
              {{item.price}}
            </em>
          </span>
          起
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  .group-title
    position:relative
    padding:.24rem 0 .26rem
    .title-img
      margin-left:.2rem
      vertical-align:top
      width:.3rem
    .title
      display:inline-block
      margin-left:.08rem
      height:.44rem
      color:#212121
      font-size:.32rem
      line-height:.44rem
    .more-title
      position:absolute
      top:.36rem
      right:.32rem
      color:#616161
      font-size:.24rem
      line-height:.28rem
      .iconfont
        margin-left:.04rem
  .hotsale-list
    padding:0 .24rem
    overflow-x:scroll;
    white-space:nowrap;
    .hotsale-item
      display:inline-block;
      margin-left:.12rem
      padding:.06rem 0 .2rem
      width:2rem
      .hotsale-imgcon
        width:2rem
        height:0
        padding-bottom:100%
        .imgcon
          width:100%
      .hotsale-sight
        margin-top:.12rem
        color:#212121
        font-size:.24rem
        line-height:.32rem
        text-align:center
      .hotsale-price
        color:#616161
        font-size:.24rem
        line-height:.36rem
        text-align:center
        .price
          color:#ff8300
          .price-num
            color:#ff8300
            font-size:.28rem
</style>

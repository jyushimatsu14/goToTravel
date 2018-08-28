<template>
  <div>
    <div class="top">
      <img class="title-img"
           src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png">
      <span class="title">猜你喜欢</span>
    </div>
    <ul class="like-list">
      <li class="item border-bottom"
          v-for="item of likeList"
          :key="item.id">
        <div class="item-imgcon">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <div class="item-title">{{item.title}}</div>
          <div class="item-comment">
            <span class="comment-num">{{item.comment}}条评论</span>
          </div>
          <div class="item-price">
            <span class="like-price">￥<em class="price">{{item.price}}</em>
            </span>
              起
            <span class="item-address">
              {{item.address}}
            </span>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeLike',
  props: {
    likeList: Array
  }
}
</script>

<style lang="stylus" scoped>
 @import '~styles/mixins.styl'
  .top
    padding:.24rem 0 .26rem
    .title-img
      display:inline-block
      overflow:hidden
      margin-left:.2rem
      width:.3rem
      height:.3rem
      vertical-align:top
    .title
      display:inline-block
      margin-left:.08rem
      line-height:.44rem
      color:#212121
      height:.44rem
      font-size:.32rem
    .item
      overflow:hidden
      display:flex
      height:1.9rem
      background:red
      .item-img
        width:1.7rem
        height:1.7rem
        padding:.1rem
      .item-info
        flex:1
        padding:.1rem
        .item-title
          line-height:.54rem
          font-size:.32rem
  .like-list
    margin-left:.24rem
    list-style:none
    .item
      position:relative
      display:list-item
      overflow:hidden
      padding:.2rem 0
      .item-imgcon
        float:left
        overflow:hidden
        width:2rem
        height:2rem
        .item-img
          width:100%
      .item-info
        overflow:hidden
        padding-left:.22rem
        .item-title
          margin-top:.26rem
          width:100%
          height:.44rem
          white-space:nowrap
          color:#212121
          font-size:.32rem
          line-height:.44rem
          ellipsis()
        .item-comment
          margin-top:.14rem
          height:.34rem
          .comment-num
            color:#616161
            font-size:.24rem
            line-height:.34rem
            vertical-align:text-bottom
        .item-price
          position:relative
          margin-top:.22rem
          color:#616161
          font-size:.24rem
          line-height:.4rem
          .like-price
            color:#ff8300
            .price
              padding-left:0
              font-style:normal
              font-size:.4rem
          .item-address
            position:absolute
            right:.24rem
            bottom:0
</style>

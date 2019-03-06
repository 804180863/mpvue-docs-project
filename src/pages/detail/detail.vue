<template>
  <div id="detailContainer">
    <p class="bookName">{{booksList.title}}</p>
    <img :src="booksList.image" alt="">
    <div class="bookInfo">
      <span>作者: {{booksList.author}}</span>
      <span>出版社: {{booksList.publisher}}</span>
      <span>出版日期: {{booksList.pubdate}}</span>
      <span>定价: {{booksList.price}}</span>
    </div>
    <button>收藏该文章</button>
    <article class="authorInfo">
      <h1>作者简介</h1>
      <section>{{booksList.author_intro}}</section>
    </article>
    <article class="contentInfo">
      <h1>文章简介</h1>
      <section>{{booksList.summary}}</section>
    </article>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        booksList: []
      }
    },
    mounted(){
      this.booksList = JSON.parse(this.$mp.query.booksList)
      
      wx.setNavigationBarTitle({
        title: this.booksList.title
      })
    }
}
  
</script>

<style lang="stylus" rel="stylesheet/stylus">
  #detailContainer
    display flex
    flex-direction column
    .bookName
      font-size 40rpx
      line-height 80rpx
      font-weight 700
      text-align center
    img
      width 70%
      height 700rpx
      margin 20rpx auto
    .bookInfo
      display flex
      flex-direction column
      font-size 32rpx
      width 100%
      padding-left 15%
    button
      width 300rpx
      height 60rpx
      font-size 32rpx
      line-height 60rpx
      margin 20rpx auto
    article
      width 100%
      padding 10%
      box-sizing border-box
      h1
        text-align center
        color #02a774
        font-weight bold
      section
        font-size 34rpx
        text-indent 34rpx

</style>
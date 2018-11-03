<template>
  <div class="container">
    <div class="imgContainr">
      <image  mode="scaleToFill" src="../../images/1.jpg" style="width: 100%;opacity: .8;"></image>
    </div>
    <div class="mainContainer">
      <div class="main-header">
        <div class="main-log">
          <image :src="log" alt="" style="width: 100%; height: 100%;"></image>
        </div>
        <div class="content">
          <h1>哈弗英语 (塘桥教学点)</h1>
          <div class="descContent">
            {{ getMessage }}
          </div>
          <p class="showHide" @click="showHideFn(showhide)">{{ showhide ?  '收起' : '查看更多'}}</p>
        </div>
      </div>
      <div class="contractstyle">
        <div class="item">
          <div class="left">
            <span class="icon"><i class="iconfont icon-dingwei1"></i></span>
            <div class="item-content">
              <p class="title">茂兴路88号仁恒广场302室</p>
              <p class="subtitle">距地铁4号线塘桥站3号口步行610m</p>
            </div>
          </div>
          <span class="iphone"><i class="iconfont icon-dianhua"></i></span>
        </div>
        <div class="item">
          <div class="left">
            <span class="icon"><i class="iconfont icon-shizhong"></i></span>
            <div class="item-content">
              <p class="title line-height">周一至周日 09:00 - 21:00</p>
            </div>
          </div>
        </div>
      </div>
      <div class="jieshouContainer">
        <div class="tabbar">
          <div class="tabbar-item" :class="{unselected: selectIndex === 0}" @click="selectIndex = 1">
            门店介绍
            <p class="border" v-show="selectIndex === 1"></p>
          </div>
          <div class="tabbar-item" :class="{unselected: selectIndex === 1}" @click="selectIndex = 0">
            门店风采
            <p class="border" v-show="selectIndex === 0"></p>
          </div>
        </div>
      </div>
      <div class="lilinag" v-show="selectIndex === 1">
        <div class="liliang-header">师资力量</div>
        <scroll-view scroll-x style="height: 160px;overflow:hidden;white-space:nowrap;width: 100%;box-sizing:border-box;padding: 0 5px;">
          <div class="itemli" v-for="(item, index) in imgList" :key="index">
            <div class="img">
              <img src="../../images/log.jpg" alt="">
            </div>
            <div class="bottomContent">
              <p class="first">Daniel</p>
              <p>英语外教</p>
              <p>6年任教</p>
            </div>
          </div>
        </scroll-view>
      </div>
      <div class="huanjing" v-show="selectIndex === 0">
        <div class="huan-title">环境</div>
        <div class="huanImgContainer">
          <div class="img-item" v-for="(item, index) in huanImages" :key="index">
            <img src="../../images/1.jpg" alt="">
          </div>
        </div>
        <p class="huan-more" @click="loadmore()">{{ loadMoreTest }}</p>
      </div>
    </div>
    <button class="btn">预约试听</button>
  </div>
</template>

<script>
import log from '../../images/log.jpg'
export default {
  data () {
    return {
      showhide: false,
      log: log,
      message: `西象教育成立于2008年，是一家专业从事中小学学习能力辅导与培养的机构
        西象教育成立于2008年，是一家专业从事中小学学习能力辅导与培养的机构
        西象教育成立于2008年，是一家专业从事中小学学习能力辅导与培养的机构
        西象教育成立于2008年，是一家专业从事中小学学习能力辅导与培养的机构
        西象教育成立于2008年，是一家专业从事中小学学习能力辅导与培养的机构
        西象教育成立于2008年，是一家专业从事中小学学习能力辅导与培养的机构`,
      selectIndex: 1,
      imgList: [1, 2, 3, 4, 5, 6],
      huanImages: [1, 2, 3, 4],
      loadMoreTest: '加载更多',
      loadmoreIndex: 0
    }
  },
  components: {
  },
  created () {
  },
  computed: {
    getMessage () {
      console.log('showhide', this.showhide)
      if (this.showhide) {
        return this.message
      }
      return this.message.substring(0, 55) + ' ...'
    }
  },
  methods: {
    showHideFn (showhide) {
      console.log('showhide', showhide)
      this.showhide = !showhide
    },
    loadmore () {
      if (this.loadmoreIndex === 0) {
        this.loadMoreTest = '收起'
        this.loadmoreIndex = 1
        this.huanImages.push(5, 6, 7, 8)
      } else {
        this.loadMoreTest = '加载更多'
        this.loadmoreIndex = 0
        this.huanImages.push(5, 6, 7, 8)
      }
    }
  }
}
</script>
<style scoped>
.mainContainer {
  position: absolute;
  top: 20%;
  left: 0;
  width: 100%;
}
.main-header {
  width: 90%;
  background: #fff;
  margin: 0 auto;
  border-radius: 5px;
  box-shadow: 0 6px 4px #eaeaea;
  position: relative;
}
.main-log {
  width: 50px;
  height: 50px;
  border: 1px solid #000;
  position: absolute;
  left: 50%;
  top: 0;
  transform: translate(-50%, -50%);
}
.main-log .logimg {
  width: 100%;
  height: 100%;
}
.content {
  padding-top: 30px;
}
.content h1 {
  text-align: center;
  font-weight: 600;
}
.descContent {
  font-size: 13px;
  padding: 10px 20px;
  line-height: 20px;
}
.showHide {
  line-height: 38px;
  text-align: center;
  font-size: 12px;
  color: #ccc;
}
.contractstyle {
  width: 90%;
  margin: 10px auto;
}
.item{
  display: flex;
  justify-content: space-between;
  padding: 8px 0;
  border-bottom: 1px solid #F2F2F2;
}
.item .left{
  display: flex;
}
.item .left .icon, .item .iphone{
  line-height: 40px;
}
.line-height{
  line-height: 40px;
}
.item .iphone i{
  font-size: 20px;
  color: rgb(67, 149, 196);
}
.item-content{
  margin-left: 4px;
}
.item-content .title{
  font-size: 15px;
}
.item-content .subtitle{
  color: #3b3838;
  font-size: 12px;
}
.tabbar{
  display: flex;
  justify-content: center;
  font-size: 14px;
  font-weight: 600;
}
.tabbar-item{
  margin: 0 10px;
}
.border{
  width: 30px;
  height: 3px;
  margin: 10px auto;
  background: #000;
}
.unselected{
  color: #ccc;
}
.lilinag{
  padding-bottom: 100px;
}
.liliang-header{
  padding-left: 10px;
  font-size: 16px;
  margin-bottom: 10px;
}
.lilinag .itemli{
  width: 100px;
  height: 100%;
  position: relative;
  margin: 0 5px;
  display:inline-block;
}
.img{
  width: 50px;
  height: 50px;
  margin: 0 auto;
  position: relative;
  z-index: 100;
}
.img img{
  width: 100%;
  height: 100%;
  border-radius: 50%;
}
.bottomContent{
  position: absolute;
  left: 0;
  top: 20px;
  width: 100%;
  bottom: 4px;
  background: #fff;
  box-shadow: 0 0 5px #ccc;
}
.bottomContent p{
  font-size: 13px;
  text-align: center;
}
.first{
  margin-top: 40px;
}
.btn{
  position: fixed;
  left: 50%;
  transform: translateX(-50%);
  bottom: 20px;
  width: 120px;
  height: 50px;
  text-align: center;
  border-radius: 30px;
  line-height: 50px;
  background: -webkit-linear-gradient(left,rgb(33, 108, 158),rgb(18, 136, 156));
  color: #FFF;
  font-size: 16px;
}
.huanjing{
  padding: 0 10px;
}
.huan-title{
  font-size: 16px;
  font-weight: 600;
}
.huanImgContainer{
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}
.img-item{
  width: 48%;
  height: 150px;
  margin: 5px auto;
}
.img-item img{
  width: 100%;
  height: 100%;
}
.huan-more{
  text-align: center;
  font-size: 12px;
  line-height: 30px;
  color: #ccc;
}
</style>

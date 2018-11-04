<template>
 <div class="page-experience">
  <div class="header">
    <div class="left">
      <span>预约礼</span>
    </div>
    <div class="right">
      <p>免费试听<span>时长20分钟</span></p>
      <p>到店礼<span>精美小礼品一份+学术能力水平测试</span></p>
    </div>
  </div>
  <div class="iphone">
    <h1>预约后我们将通过电话联系您</h1>
    <input type="text" placeholder="请输入手机号码" class="inputiphone">
    <p><i class="iconfont icon-yduidunpaishixin"></i><span>无强行推销</span> <i class="iconfont icon-yduidunpaishixin"></i><span>号码仅此商户可见</span></p>
  </div>
  <button class="btn">立即预约</button>
 </div>
</template>

<script>
export default {
  data () {
    return {

    }
  },
  components: {

  },
  methods: {
    openLocation () {
      wx.getLocation({
        type: 'gcj02', // 返回可以用于wx.openLocation的经纬度
        success (res) {
          const latitude = res.latitude
          const longitude = res.longitude
          wx.openLocation({
            latitude,
            longitude,
            scale: 28
          })
        }
      })
    }
  }

}
</script>

<style scoped>
.header {
  display: flex;
  font-size: 14px;
  padding: 15px 5px;
  background: #FFFCEE;
}
.left {
  width: 15%;
  text-align: right;
}
.left span {
  margin-right: 4px;
  font-size: 12px;
  color: orange;
  padding: 0 4px;
  border: .5px solid orange;
}
.right p span {
  font-size: 12px;
  margin-left: 4px;
  color: #ccc;
}
.iphone {
  margin-top: 10px;
  padding: 10px;
}
.iphone h1{
  font-size: 16px;
  font-weight: 500;
  margin-bottom: 10px;
}
.inputiphone {
  outline: none;
  border: 1px solid #eaeaea;
  background: #eaeaea;
  border-radius: 20px;
  height: 40px;
  font-size: 14px;
  padding-left: 10px;
  color: #eaeaea;
}
.iphone p span {
  font-size: 12px;
  margin-right: 10px;
}
.btn {
  position: fixed;
  left: 2%;
  width: 96%;
  bottom: 10px;
  border-radius: 20px;
  background: #FF7A22;
  font-size: 14px;
  color: #fff;
}
.iconfont{
  display: inline-block;
  vertical-align: middle;
  color: green;
}
</style>

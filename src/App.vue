<script>
export default {
  created () {
    // 调用API从本地缓存中获取数据
    const logs = wx.getStorageSync('logs') || []
    logs.unshift(Date.now())
    wx.setStorageSync('logs', logs)

    console.log('app created and cache logs by setStorageSync')
  }
}
</script>

<style>
/* this rule will be remove */
* {
  transition: width 2s;
  -moz-transition: width 2s;
  -webkit-transition: width 2s;
  -o-transition: width 2s;
}
page{
  margin: 0;
  padding: 0;
  width: 100%;
  overflow-x: hidden;
}
@font-face {
  font-family: 'iconfont';  /* project id 896497 */
  src: url('//at.alicdn.com/t/font_896497_rn0s15hhi7i.eot');
  src: url('//at.alicdn.com/t/font_896497_rn0s15hhi7i.eot?#iefix') format('embedded-opentype'),
  url('//at.alicdn.com/t/font_896497_rn0s15hhi7i.woff') format('woff'),
  url('//at.alicdn.com/t/font_896497_rn0s15hhi7i.ttf') format('truetype'),
  url('//at.alicdn.com/t/font_896497_rn0s15hhi7i.svg#iconfont') format('svg');
}

.iconfont {
  font-family:"iconfont" !important;
  font-size:16px;
  font-style:normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.icon-shizhong:before { content: "\e787"; }

.icon-yduidunpaishixin:before { content: "\e67e"; }

.icon-dingwei1:before { content: "\e617"; }

.icon-dianhua:before { content: "\e6f9"; }
</style>

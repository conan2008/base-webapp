<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">ZBC 8121</router-link>|
      <router-link to="/about">About212</router-link>
      <button @click="handleClick" style="width: 50px; height: 50px; border: 1px solid green;">点我</button>
    </div>
    <router-view />
  </div>
</template>
<script>
export default {
  created () {
    console.log(123)
    console.log(window)
    setTimeout(() => {
      console.log(window.navigator.userAgent)
      console.log('sss', wx.chooseImage)
    }, 1000)

    // wx.config({
    //   debug: true, // 开启调试模式,调用的所有api的返回值会在客户端alert出来，若要查看传入的参数，可以在pc端打开，参数信息会通过log打出，仅在pc端时才会打印。
    //   appId: 'wxc0688c5c8b980317', // 必填，公众号的唯一标识
    //   timestamp: '', // 必填，生成签名的时间戳
    //   nonceStr: '', // 必填，生成签名的随机串
    //   signature: '', // 必填，签名
    //   jsApiList: ['chooseImage'] // 必填，需要使用的JS接口列表
    // })
  },
  methods: {
    handleClick () {
      wx.ready(function () {
        wx.chooseImage({
          count: 2, // 默认9
          sizeType: ['original', 'compressed'], // 可以指定是原图还是压缩图，默认二者都有
          sourceType: ['album', 'camera'], // 可以指定来源是相册还是相机，默认二者都有
          success: function (res) {
            console.log(res)
          }
        })
      })
    }
  }
}
</script>
<style lang="scss">
</style>

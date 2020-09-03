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
  },
  methods: {
    handleClick () {
      window.wx.chooseImage({
        count: 2, // 默认9
        sizeType: ['original', 'compressed'], // 可以指定是原图还是压缩图，默认二者都有
        sourceType: ['album', 'camera'], // 可以指定来源是相册还是相机，默认二者都有
        success: function (res) {
          console.log(res)
        }
      })
    }
  }
}
</script>
<style lang="scss">
</style>

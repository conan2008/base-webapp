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
    }, 1000)
  },
  methods: {
    handleClick () {
      console.log('checkJSApi', wx.checkJSApi)
      if (window.wx.checkJSApi()) {
        console.log(999)
        window.wx.getLocalImgData({
          localId: '', // 图片的localID
          success: function (res) {
            console.log(res) // localData是图片的base64数据，可以用img标签显示
          }
        })
      }
    }
  }
}
</script>
<style lang="scss">
</style>

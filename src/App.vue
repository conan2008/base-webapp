<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">ZBC 8121</router-link>|
      <router-link to="/about">About212</router-link>
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

    console.log(wx.miniProgram)
    if (wx.miniProgram.checkJSApi) {
      wx.gminiProgram.etLocalImgData({
        localId: '', // 图片的localID
        success: function (res) {
          console.log(res) // localData是图片的base64数据，可以用img标签显示
        }
      })
    }
  }
}
</script>
<style lang="scss">
</style>

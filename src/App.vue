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
  }
}
</script>
<style lang="scss">
</style>

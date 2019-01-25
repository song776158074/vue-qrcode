<template>
  <div id="app">
    <div><input v-model="text"/></div>
    <qrcode :url="text" :iconurl="img"></qrcode>
  </div>
</template>

<script>
import qrcode from './qrcode/qrcode.vue'
export default {
  name: 'home',
  data(){
      return{
        num:80,
        imgnum:40,
        img:require("./assets/logo.png"),
        text:"www.baidu.com",
      }
  },
  components: {
    qrcode
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
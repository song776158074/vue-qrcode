<template>
<div class="qrcode" >
  <img :src="this.iconurl" class="logoimg" :style="imgstyle" v-if="iconurl==='0'?false:true"/>
  <div ref="qrCodeUrl" id="qrcode">
  </div>
</div>
</template>

<script>
import QRCode from 'qrcodejs2'
export default {
  name: 'qrcode',
  data(){
      return{
        img:'https://cn.vuejs.org/images/logo.png',
        imgstyle:{width:this.imgwid+'px',height:this.imghei+'px', marginTop:'-'+this.imgwid/2+'px',marginLeft:'-'+this.imghei/2+'px'},
      }
  },
  mounted(){
     this.creatQrCode()
  },
  methods:{
      creatQrCode() {
        document.getElementById('qrcode').innerHTML = "";
        let qrcode = new QRCode(this.$refs.qrCodeUrl, {
            text: this.url,
            width: this.wid,
            height: this.hei,
            colorDark: this.colorDark,//二维码颜色
            colorLight: this.colorLight,//二维码背景
            correctLevel: QRCode.CorrectLevel.H//容错级别
        })
      }
  },
  props: {
    url: {
      type: String,
      default: 'www.baidu.com'
    },
    wid: {
      type: Number,
      default: 70
    },
    hei: {
      type: Number,
      default: 70
    },
    imgwid: {
      type: Number,
      default: 30
    },
    imghei: {
      type: Number,
      default: 30
    },
    colorDark: {
      type: String,
      default: '#000000'
    },
    colorLight: {
      type: String,
      default: '#ffffff'
    },
    iconurl: {
      type: String,
      default: '0'
    }
  },
  watch: {
    url:{ //深度监听，可监听到对象、数组的变化
      handler (newV, oldV) {
          if(newV!=oldV){
            this.creatQrCode()
          }
        },
        deep:true  
    },
    iconurl:{ //深度监听，可监听到对象、数组的变化
      handler (newV, oldV) {
          if(newV!=oldV){
            this.creatQrCode()
          }
        },
        deep:true  
    }
  },
}
</script>
<style>
.qrcode{
  display:inline-block;
  position:relative;
}
.logoimg{
    position:absolute;
    left:50%;
    top:50%;
}
</style>
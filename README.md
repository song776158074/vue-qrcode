# qrcode

> 基于qrcode.js二维码封装的vue组件

## Install

```
npm install vue_qrcodes
or
yarn add vue_qrcodes
```

## Example

[Demo]

```
<template>
<div>
    <qrcode url="www.baidu.com" iconurl="https://cn.vuejs.org/images/logo.png"></qrcode>
</div>
</template>

<script>
import qrcode from 'vue_qrcodes'
export default {
  name: 'qrcode',
  components:{
      qrcode
  }
}
</script>
```

![](http://html.yangguanghaina.com:8081/demo.jpg)

## Props

| Property | Description | Type | Accepted Values | Default |
|-|-|-|-|-|
| url | 二维码输入的内容 | String | - | www.baidu.com |
| iconurl | 二维码中间小图片地址 | String | - | https://cn.vuejs.org/images/logo.png |
| wid | 二维码宽度 | Number | - | 70 |
| hei | 二维码高度 | Number | - | 70 |
| colorDark | 二维码颜色 | String | - | #000000 |
| colorLight | 二维码背景色 | String | - | #ffffff |
| imgwid | 二维码中间小图片宽度 | Number | - | 30 |
| imghei | 二维码中间小图片高度 | Number | - | 30 |
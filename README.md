## 使用方法（主要看pages/hch-poster页面的例子）

```
<hchPoster ref="hchPoster" :canvasFlag.sync="canvasFlag" @cancel="canvasCancel" :posterObj.sync="posterData"/>
<view :hidden="canvasFlag">
	<canvas class="canvas"  canvas-id="myCanvas" ></canvas><!-- 海报 -->
</view>
```
```

import hchPoster from '../../wxcomponents/hch-poster/hch-poster.vue'

components:{
	hchPoster,
},
```
## 使用方法
```
createCanvasImageEvn(){
	Object.assign(this.posterData,
	{
		url:'https://img0.zuipin.cn/mp_zuipin/poster/hch-pro.jpg',//商品主图
		icon:'https://img0.zuipin.cn/mp_zuipin/poster/hch-hyj.png',//会员价图标
		title:"诗酒茶系列 武夷大红袍 2018年 花香型中火 一级 体验装 16g",//标题
		discountPrice:"250.00",//折后价格
		orignPrice:"300.00",//原价
		code:'https://img0.zuipin.cn/mp_zuipin/poster/hch-code.png',//小程序码
	})
this.$forceUpdate();//强制渲染数据
setTimeout(()=>{
	this.canvasFlag=false;//显示canvas海报
	this.deliveryFlag = false;//关闭分享弹窗
	this.$refs.hchPoster.createCanvasImage();//调用子组件的方法
},500)
},
```
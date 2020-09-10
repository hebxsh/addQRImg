qrcode.js
------
本项目引用
[生成二维码图片](https://github.com/davidshimjs/qrcodejs)生成二维码算法, 使用canvas将本地base64图片和二维码图片合成一张整图, 在Android上实现长按保存到本地, 不需上传服务器.
使用方法
------
生成背景图加二维码  

```
/**
 * @param   url			(必填)二维码地址
 * @param   imgdata 	(必填)二维码背景图	(非跨域图片base64数据);
 * @param   width   	二维码宽度			(默认256)
 * @param   x       	二维码位置x			(默认0)
 * @param   y       	二维码位置y			(默认0)
 * @param   colorDark		黑块颜色		(默认#000000)
 * @param   colorLight		白底颜色		(默认#ffffff)
 * @param   correctLevel	纠错等级		(默认2, 1=7%,0=15%,3=20%,2=30%)
 * */
QRCode.addQRImg({
    url:"your url text more...",
    data:imgdata,
    width:275,
    x:50,
    y:50
},function(img){
    document.body.appendChild(img);
});
```
仅生成二维码  

```
/**
 * @param   url			(必填)二维码地址
 * @param   width   	二维码宽度			(默认256)
 * @param   colorDark		黑块颜色		(默认#000000)
 * @param   colorLight		白底颜色		(默认#ffffff)
 * @param   correctLevel	纠错等级		(默认2, 1=7%,0=15%,3=20%,2=30%)
 * */
QRCode.addQRImg({
    url:"your url text more...",
    width:275,
    colorDark:"#ff0000",
    correctLevel:2
},function(img){
    document.body.appendChild(img);
});
```
获取二维码数据  

```
/**
 * @param   text				(必填)二维码地址
 * @param   correctLevel	纠错等级	(默认2, 1=7%,0=15%,3=20%,2=30%)
 * */
let qrdata = new QRCode.getQRdata({
    text: "your url text more...",
    correctLevel: 1
});
console.log(qrdata);
```
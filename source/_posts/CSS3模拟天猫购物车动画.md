---
title: CSS3模拟天猫购物车动画
date: 2017-08-03 16:33:56
tags:
---
话不多说，直接上代码：

<!-- more -->

``` bash
<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no, maximum-scale=1, width=device-width">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black">
    <meta name="format-detection" content="telephone=no">
    <title>模拟-天猫购物车-动画</title>
   	<style>
   		* {
			margin: 0;
			padding: 0;
		}
		body, html {
			width: 100%;
			height: 100%;
		}
		.tip {
			width: 100%;
			line-height: 24px;
			margin-top: 40px;
			color: #ff4944;
			font-size: 14px;
			text-align: center;
		}
		.tip.small {
			font-size: 10px;
		}
		.toto-box {
			width: 100%;
			height: 1.06667rem;
			line-height: 1.06667rem;
			text-align: center;
			color: #fff;
			font-size: 0.37333rem;
			position: fixed;
			left: 0;
			bottom: 0;
			display: -webkit-box;
			display: -ms-flexbox;
			display: flex;
		}
		.toto-post,
		.toto-get {
			position: relative;
			left: 0;
			top: 0;
			-webkit-box-flex: 1;
			    -ms-flex: 1;
			        flex: 1;
			height: 1.06667rem;
		}
		.toto-post {
			background: orange;
		}
		.toto-get {
			background: #ff4944;
		}
		@-webkit-keyframes movex {
			0% {
				-webkit-transform: translateX(0);
				        transform: translateX(0);
			}

			100% {
				-webkit-transform: translateX(-4.98667rem);
				        transform: translateX(-4.98667rem);
			}
		}
		@keyframes movex {
			0% {
				-webkit-transform: translateX(0);
				        transform: translateX(0);
			}

			100% {
				-webkit-transform: translateX(-4.98667rem);
				        transform: translateX(-4.98667rem);
			}
		}

		@-webkit-keyframes movey {
			0% {
				opacity: 0;
				-webkit-transform: translateY(0);
				        transform: translateY(0);
			}
			1% {
				opacity: 1;
			}
			50% {
				-webkit-transform: translateY(-6.66667rem);
				        transform: translateY(-6.66667rem);
			}
			99% {
				opacity: 1;
			}
			100% {
				opacity: 0;
				-webkit-transform: translateY(0);
				        transform: translateY(0);
			}
		}

		@keyframes movey {
			0% {
				opacity: 0;
				-webkit-transform: translateY(0) scale(1, 1);
				        transform: translateY(0) scale(1, 1);
			}
			1% {
				opacity: 1;
			}
			50% {
				-webkit-transform: translateY(-6.66667rem);
				        transform: translateY(-6.66667rem);
			}
			99% {
				opacity: 1;
			}
			100% {
				opacity: 0;
				-webkit-transform: translateY(0) scale(0.5, 0.5);
				        transform: translateY(0) scale(0.5, 0.5);
			}
		}
		.circle.active span {
			-webkit-animation: 1s ease-in-out movex forwards;
			        animation: 1s ease-in-out movex forwards;
		}
		.circle.active span i {
			-webkit-animation: 1s ease-in-out movey forwards;
			        animation: 1s ease-in-out movey forwards;
		}
		.circle-fa {
			width: 0.8rem;
			height: 0.8rem;
			position: absolute;
			left: 50%;
			top: 0;
			-webkit-transform: translate(-50%, 0);
			        transform: translate(-50%, 0);
		}
		.circle {
			width: 0.8rem;
			height: 0.8rem;
			position: absolute;
			left: 0;
			top: 0;
		}
		.circle span {
			width: 100%;
			height: 100%;
			display: block;
		}
		.circle span i {
			width: 100%;
			height: 100%;
			display: block;
			background: #108ee9;
			border-radius: 50%;
			opacity: 0;
		}
   	</style>
</head>

<body>
	<div class="tip">点击"加入购物车"即可</div>
	<div class="tip small">因为css使用了rem为单位，建议PC端打开模拟器查看效果</div>
	<section class="toto-box">
		<div class="toto-get">
			<div>购物车</div>
		</div>
		<div class="toto-post">
			<div>加入购物车</div>
			<div class="circle-fa"></div>
		</div>
	</section>
	<script>
		var oHtml = document.querySelector("html");
		oHtml.style.fontSize = document.body.clientWidth/10 + "px";

		var oTarget = document.querySelector(".toto-post");
		var oCircleFa = document.querySelector(".circle-fa");
		
		oTarget.onclick = function() {
			var oCircle = document.createElement("div");
			oCircle.innerHTML = "<span><i></i></span>";
			oCircle.classList.add("circle");
			oCircle.classList.add("active");
			oCircleFa.appendChild(oCircle);
			setTimeout(function() {
				oCircleFa.removeChild(oCircleFa.childNodes[0]);
			}, 1000);
		};
	</script>
</body>

</html>
```

[查看效果](http://totozhangzhao.github.io/totozhangzhao/demo/circle.html)(建议在移动端打开)
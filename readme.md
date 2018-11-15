# 实现鼠标悬浮于图片显示文字，离开图片文字消失
## Html结构
```
<div class="image-box">
	<ul>
		<li>
			<a href="#"><img src="./img/1.jpg" alt="杨枝甘露">
			<span><h3>杨枝甘露</h3><br>新鲜的杨桃辅以鲜美的草莓，匠心制造，爽滑可口，味道极佳，推荐指数：❤❤❤❤</span></a>
		</li>
		<li>
			<a href="#"><img src="./img/2.jpg" alt="港式双皮奶">
			<span><h3>港式双皮奶</h3>双皮奶口感细腻润滑，冬天可以趁热吃，夏天放冰箱里冰一会儿口味更佳，推荐指数：❤❤❤❤</span></a>
		</li>
	<ul>
</div>
```
在上述代码中我设置了一个图片盒子，盒子中的图片以无序列表的形式呈现，读者可以增设图片数目。在每个列表项当中我设置了一个a链接，在a链接中有我们所要显示的图片img以及在鼠标滑过时图片上所要显示的文字，用行内元素span存放，链接的href属性可以为空。
## CSS样式
```
<style type="text/css" media="screen">
		html{
			font-size: 62.5%
			font:normal 100% "微软雅黑";
		}
		* {
			padding: 0px;
			margin: 0px;
			}
		.image-box{
			width: 80%;
			height: 300px;
			margin: 50px auto;
		}
		.image-box ul{
			width: 100%; 
			height: 300px;
		}
		.image-box li{
			position:relative;
			width: 30%;
			height: 300px;
			margin: 0 10%;
			list-style: none;
			float: left;
		}	
		.image-box li a{
			text-decoration: none;
		}
		.image-box li a img{
			width:100%;
			height: 300px;
		}
		.image-box li a span{
			display: none;
		}
		.image-box li a:hover span{
			width: 100%;
			height: 300px;
			position: absolute;
			display: block;
			top: 0;
			left: 0;
			background: #000;
			font-size: 5em;
			line-height: 300px;
			text-align: center;
			color: #FFFFFF;
			opacity: 0.6;
		}
	</style>
```
在css的设置中，我首先为图片盒子，无序列表，每个链接，每个列表项及图片指定了大小，之后设置链接的属性display，使无鼠标动作时不显示文字内容只显示图片，只有在鼠标移入时，由于img标签在a标签内，所以当鼠标划过图片时，我这里设置会显示a标签下同级别的span标签，给这个a标签下的span标签加上某种样式，设置行内元素span为块状元素以便为其指定和图片相同的大小以覆盖图片。因为我的列表项采用了相对定位，所以在这里我采用了绝对定位为块状元素span，然后设置其水平垂直居中，我们想要的效果就达到了。

以上代码及解释仅来自于我个人观点，如果发现有错误也请及时纠正和告知，谢谢！
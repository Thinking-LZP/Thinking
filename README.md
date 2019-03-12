<!DOCTYPE html>

<html>

	<head>
		<meta charset="utf-8">
		<link rel="icon" href="https://www.apple.com/favicon.ico">
		<title> ThinKing </title> 	
		<base href="." target="_blank">
		<style type="text/css">
			*{margin:0px; padding:0px;}
			body{display: flex; min-width: 100vw; min-height: 100vh; font-family: KaiTi;}
			nav{overflow: hidden; width: 100vw; background-color: rgba(0,0,0,0);}
			a{display: flex; justify-content: center; align-items: center;text-decoration: none;}
			a:link {color: #e6e6e6}
			a:visited {color: #e6e6e6}
			nav a{min-height: 100vh;}
			a:hover{background-color: #283593;color: #fff;}
			main{display: flex;position:relative;min-width: 96vw;background-color: rgba(0,0,0,0);}
			fieldset{flex-direction: column;width: 350px;margin: 0 2px;}
			legend{text-align:center; color: #fff;}
			fieldset a{padding: 20px 10px; margin: 10px 5px ; border-radius: 10px; border: 2px solid #fff; font-size: 20px; background-color: rgba(0,0,0,0);}
			canvas{display: block;position : absolute;z-index:-1;min-width: 100vw; min-height: 100vh;}
		</style>

	</head>
    
	<body>

		<canvas id="LZP"></canvas>

		<nav>
		    <a href="/">H</a>
		</nav>

		<main>
			<fieldset>
				<legend>【资讯】</legend>
				<a href="https://www.mbalib.com/"   title="MBA百科">MBA lib</a>
				<a href="https://readhub.cn/topics"  title="热门快讯">Readhub</a>
				<a href="http://www.iimedia.cn/"  title="收集报告">艾媒网</a>
				<a href="https://www.jiemian.com/"  title="多杂 营销">界面网</a>
				<a href="https://www.huxiu.com/" title="商业科技资讯">虎嗅网</a>
				<a href="https://www.pintu360.com/" title="商业评论">品途网</a>
				<a href="https://www.chinaventure.com.cn/" title="金融">投中网</a>
			</fieldset>

			<fieldset>
				<legend>【bilibili】</legend>
				<a href="https://space.bilibili.com/17819768/#/video"  title="电影解说">电影最TOP</a>
				<a href="http://space.bilibili.com/927587/#/video" title="电影解说">木鱼水心</a>
				<a href="https://space.bilibili.com/100825369/video">品牌故事</a>
				<a href="https://space.bilibili.com/24127511/video">造就Talk</a>
				<a href="https://space.bilibili.com/4888022/video" title="日本综艺">人类观察</a>
				<a href="https://space.bilibili.com/26709183/#/video" title="医学">人民医学</a>
				<a href="https://search.bilibili.com/all?keyword=%E8%B6%85%E7%BA%A7%E5%85%A8%E8%83%BD%E4%BD%8F%E5%AE%85%E6%94%B9%E9%80%A0%E7%8E%8B&from_source=nav_search&order=click&duration=0&tids_1=0" title="日本综艺">住宅改造王</a>
				<a href="https://www.kanbilibili.com/rank/videos" title="哔哩哔哩总榜">哔哩总榜</a>
			</fieldset>

			<fieldset>
			  <legend>【视音】</legend>
			  <a href="https://neets.cc/">neets</a>
			  <a href="https://www.xkdy.tv/">星空</a>
			  <a href="https://www.sq688.com/" title="音乐">无损下载</a>
			  <hr>
			  <a href="https://cookpad.com/" title="日本美食">cookpa</a>
			</fieldset>

			<fieldset>
			  <legend>【设计】</legend>
			  <a href="https://www.zcool.com.cn/">站酷</a>
			  <a href="https://www.ui.cn/">UI</a>
			  <a href="http://www.pptbz.com/">PPT宝藏</a>
			  <a href="http://www.shejidaren.com/">设计达人</a>
			</fieldset>

			<fieldset>
			  <legend>【博客】</legend>
			  <a href="http://shihb.blog.sohu.com/" title="时寒冰说">时寒冰</a>
			  <a href="http://www.ruanyifeng.com/blog/weekly/" title="网络周刊">阮一峰</a>
			</fieldset>

			<fieldset>
			  <legend>【文档|图片】</legend>
			  <a href="https://mubu.com/login" title="文档收藏">幕布</a>
			  <a href="https://kgbook.com/"  title="电子书">苦瓜</a>
			  <a href="https://shuge.org/"   title="古书籍">书格</a>
			  <hr>
			  <a href="https://withpinbox.com/" title="图片收藏">Pinbox</a>
			</fieldset>

			<fieldset>
			  <legend>【Web】</legend>
			  <a href="https://www.w3cschool.cn/">w3cschool</a>
			  <a href="http://alloyteam.github.io/CodeGuide/#css-miscellaneous" title="CSS">HTML</a>
			  <a href="https://www.w3cplus.com/" title="CSS">w3cplus</a>
			</fieldset>


			<fieldset>
				<legend>【Young】</legend>
				<a href="https://sspai.com/">少数派</a>
				<a href="https://www.ifanr.com/">爱范儿</a>
				<a href="https://post.smzdm.com/">什么值得买</a>
			</fieldset>
	  	</main>

		<script type="text/javascript">

		    var LZP = document.getElementById("LZP");//初始化画布
		    var ctx = LZP.getContext("2d");//2维
		 
		    LZP.height = window.innerHeight;
		    LZP.width = window.innerWidth;

		    var chinese = "0 1";//画布显示字符
		    chinese = chinese.split("");
		 
		    var font_size = 16;//字符大小
		    var columns = LZP.width / font_size;
		    var drops = [];
		    for (var x = 0; x < columns; x++)
		        drops[x] = 1;

		    function draw() //绘制 Matrix (矩阵) 函数
		    {
		        ctx.fillStyle = "rgba(0, 0, 0, 0.1)"; //fill(填充) 数字颜色透明渐变的效果
		        ctx.fillRect(0, 0, LZP.width, LZP.height); //填充字符位置
		        ctx.fillStyle = "#0F0"; //填充字符的颜色
		        ctx.font = font_size + "px";//字符大小的单位

		        for (var i = 0; i < drops.length; i++)
		        {  
		            var text = chinese[Math.floor(Math.random() * chinese.length)];//字符随机
		            
		            ctx.fillText(text, i * font_size, drops[i] * font_size);
		 
		            if (drops[i] * font_size > (LZP.height*2/3) && Math.random() > 0.85)
		                drops[i] = 0;
		            drops[i]++;
		        }
		    }
		 
		    setInterval(draw, 50);//按照指定间隔一直执行方法
		</script>
	</body>
</html>

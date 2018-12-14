使用vue-cli搭建项目开发环境
配置sass环境，
	1、安装sass的依赖包
	npm install --save-dev sass-loader
	//sass-loader依赖于node-sass
	npm install --save-dev node-sass
	2、在build文件夹下的webpack.base.conf.js的rules里面添加配置
	{
	  test: /\.sass$/,
	  loaders: ['style', 'css', 'sass']
	}
	3、在APP.vue中修改style标签
	<style lang="scss">
	4、然后运行项目
	$ npm run dev
	修改APP.vue的样式看下效果 
	$background:#ccc;
	body{
		background: $background
	}
开发头部和导航的组件，直接在app.vue中引入，因为头部和导航需要每个页面都有
	开发导航的时候犯了一个低级错误，将v-for写在了ul标签上，应该写在li标签上
开发首页----创建index文件夹并创建index.vue文件
	首页有爆款模块，开发了商品item，图片是使用的本地下载的图片，一开始老是不显示，路径是对的但是怎么都不显示，上网查了一下，
	我的图片放在了assets文件夹里，引入要使用import img from '.....', 或者 src:require('......');如果放在static里就不用这么麻烦，直接引用就可以.
	给商品li hover时添加红色边框，元素抖动，解决：给li一开始就添加和背景色一样的边框，hover时改变边框颜色
	还有近期热销模块，这个模块是新建hotSell.vue单独写的，往index.vue引入时提示<hotsell></hotsell>没有注册，原因：引入时使用的大驼峰HotSell，在
复制了淘宝reset文件重置css样式标签中使用应该使用‘-’形式<hot-sell></hot-sell>而不是<hotsell></hotsell>

开发明日预告模块下面想显示优惠券剩余,刚开始设置z-index无效，后来又给需要z-index的元素添加了position:absolute才有效.接着又有一个问题，移入li（父元素）让剩余优惠券（子元素）显示，
一开始使用vue的v-if ，定义初始数据，发现不行，最后还是使用的css：hover方法（fu:hover zi{...这样可以控制子元素的样式}）





git add .
git commit -m 'msg'
git checkout master
git merge mybranch
git push origin master

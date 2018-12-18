<template>
  <div id="app">
  		<!--  header start  -->
			<div id="header">
				<div class="siteBox">
				<p>欢迎来到。。。</p>
				</div>
				<div class="navBox">
					<ul class="navList">
						<li 
							v-for="(list,index) in navLists" 
							@click="currentIndex = index" 
							:class="{active: index === currentIndex}"
							class="navBarList"
						>
							{{list.title}}
						</li>
					</ul>
				</div>
			</div>
			<!--  header end  -->
			<index v-show="currentIndex == 0"></index>
			<women v-show="currentIndex == 1"></women>
			<!--  footer start  -->
			<div class="footer">
				<img src="static/wx.jpg"/>
			</div>
			<!--  footer end  -->
  </div>
</template>

<script>
	import Index from './pages/index/index'
	import Women from './pages/women/index'
export default {
  name: 'App',
  data(){
  	return {
  		currentIndex: 0,
				navLists: [
					{id: 1, title: '首页'},
					{id: 2, title: '女装'},
					{id: 3, title: '男装'},
					{id: 4, title: '内衣'},
					{id: 5, title: '母婴'},
					{id: 6, title: '化妆品'},
					{id: 7, title: '居家'},
					{id: 8, title: '美食'},
					{id: 9, title: '鞋包配饰'},
					{id: 10, title: '数码家电'},
					{id: 11, title: '文体车品'}
				]
  	}
  },
  components: {
  	Index,
  	Women
  }
}
</script>

<style lang="scss">
	/*  header  */
	.siteBox{
		width: 100%;
		height: 30px;
		background: #000;
		color: #ccc;
	}
	/* nav */
	.navBox{
		width: 100%;
		height: 46px;
		line-height: 46px;
		background: #f00;
		.navList{
			width: 90%;
			height: 100%;
			margin: 0 auto;
			display: flex;
			justify-content: space-around;
			align-items: center;
			.navBarList{
				width: 84px;
				height: 30px;
				color: #fff;
				font-family: 'Microsoft YaHei';
				border-radius: 20px;
				cursor: pointer;
				text-align: center;
				line-height: 30px;
				font-size: 18px;
				transition: background 0.5s, color 0.5s
				/*background: #26A2FF;*/
			}
			.active{
				background: #fff;
				color: #ff5151;
			}
			.navBarList:hover{
				background: #fff;
				color: #ff5151;
			}
		}
	}
	
	/* footer */
		.footer{
			width: 100%;
			height: 120px;
			background: #f00;
			text-align: center;
			line-height: 120px;
		img{
			height: 100px;
			display: inline-block; 
			vertical-align: middle;
		}
	}

</style>

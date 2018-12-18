<template>
	<div>
		
	</div>
</template>

<script>
	export default{
		name: 'site',
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
		}
	}
</script>

<style lang="scss">
	
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
</style>
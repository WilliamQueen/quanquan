<template>
	<div id="index">
		<div class="mainBox">
			<div id="shouye">
				<baokuan></baokuan>
				<hot-sell></hot-sell>
				<notice></notice>
			</div>
		</div>
		
	</div>
</template>

<script>
	import Baokuan from './Baokuan' 
	import HotSell from './hotSell' 
	import Notice from './notice' 
	export default{
		name: 'index',
		components: {
			Baokuan,
			HotSell,
			Notice
		},
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
		created() {
			
		},
		mounted() {
			
		}
	}
</script>

<style lang="scss">
	
	
	.mainBox{
		width: 90%;
		margin: 0 auto;
	}
	.bodyBox{
		margin-top: 10px;
		overflow:hidden;
		background: #fff;
		.goodsClass{
			height: 30px;
			line-height: 30px;
			font-size: 14px;
			color: #333;
			border-bottom: 1px dashed #ccc;
			display: flex;
			justify-content: space-between;
			.hotBuy {
				margin-left: 4px;
				img{
					height: 18px;
					width: 18px;
					margin-left: 4px;
				}
			}
			a{
				color: #ff5151;
			}
			a:hover{
				text-decoration: underline;
				color: #f00;
			}
		}
		.goodsWrapper{
			/*width: 2500px;*/
			width: 1280px;
			overflow: hidden;
			height: 420px;
			ul{
				width: 2200px;
			}
		}
		li{
			width: 250px;
			height: 408px;
			float: left;
			margin-right: 16px;
			margin-top: 8px;
			border: 1px solid #ccc;
			.yhqbg{
				width: 150px;
				height: 50px;
				margin: 8px auto;
				cursor: pointer;
				background: url(../../assets/images/icon/bg.gif) no-repeat;
				background-size:100% ;
				position: relative;
				.jumpOutside{
					width: 100%;
					height: 100%;
					display: block;
					margin-left: -1px;
					.yhPrice{
						width: 50px;
						height: 30px;
						text-align: center;
						font-size: 28px;
						color: #ffca66;
						position: absolute;
						right: 40px;
						top: 8px;
					}
				}
				.jumpOutside:hover{
					border: 1px solid #333;
					box-shadow: 0 0 4px #333
				}
			}
		}
		li:hover{
			border: 1px solid #f00;
			box-shadow: 0 0 4px red
		}
		.goodsImg{
			width: 250px;
			height: 250px;
			cursor: pointer;
		}
		.curtailInfo {
			.goodsTitle{
				margin-top: 2px ;
				height: 45px;
				width: 99%;
				line-height:22px ;
				font-size: 14px;
				overflow: hidden;
			}
			.goodsTitle:hover{
				text-decoration: underline;
			}
			.goodsPrice{
				width: 100%;
				height: 30px;
				line-height: 30px;
				color: #f00;
				display: flex;
				justify-content: space-around;
				.goodsBeforPrice{
					font-size: 8px;
					color: #000;
					text-decoration: line-through;
					line-height: 32px;
				}
				.LastPriceBox{
					display: flex;
					justify-content: space-around;
					text-align: center;
					span{
						font-size: 20px;
					}
				}
			}
		}
	}
</style>
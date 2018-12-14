<template>
	<div id="index">
		<div class="mainBox">
			<div class="bodyBox">
				<div class="goodsClass">
					<div class="hotBuy">爆款<img src="../../assets/images/icon/rexiao.png" alt="" /></div>
					<a href="#">更多 >></a>
				</div>
				<div class="goodsWrapper" ref="wrapper">
					<ul class="goodsContent">
						<li v-for="item in goodsItem" :key="item.id">
							<img class="goodsImg" :src="item.src"/>
							<div class="curtailInfo">
								<p class="goodsTitle"><a href=":;javascript">大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴</a></p>
								<div class="goodsPrice">
									<div class="LastPriceBox">
										<img src="../../assets/images/icon/quanhoujia.png"/>
										<p class="goodsLastPrice">￥<span>39.90</span></p>
									</div>
									<p class="goodsBeforPrice">原价：￥<span>39.90</span></p>
								</div>
							</div>
							<!--优惠券图片-->
							<div class="yhqbg">
								<p class="yhPrice">200</p>
							</div>
						</li>
					</ul>
				</div>
			</div>
			<hot-sell :lists="goodsItem"></hot-sell>
			<notice></notice>
		</div>
	</div>
</template>

<script>
	import BScroll from 'better-scroll' 
	import HotSell from './hotSell' 
	import Notice from './notice' 
	export default{
		name: 'index',
		components: {
			HotSell,
			Notice
		},
		data(){
			return {
				goodsItem: [
					{id: 1, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
					{id: 2, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
					{id: 3, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
					{id: 4, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
					{id: 5, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
					{id: 6, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
					{id: 7, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
					{id: 8, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
				],
				goodsClass: [
					{id: 1, title: '爆款', icon: "../../static/icon/rexiao.png"},
					{id: 2, title: '热销产品', icon: "../../static/icon/rexiao.png"},
					{id: 3, title: '明日预告', icon: "../../static/icon/rexiao.png"},
					
				]
			}
		},
		mounted() {
//		    this.getSingerData()
			this.$nextTick(() => {
				console.log(this)
		        let bscrollDom = this.$refs.wrapper;
		        this.aBscroll = new BScroll(bscrollDom,{
		        	click: true,
		        	scrollX: true
		        })
		    })
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
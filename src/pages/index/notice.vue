<template>
	<div id="notice">
		<div class="noticeBox">
			<div class="goodsClass">
				<div class="hotBuy">明日预告<img src="../../assets/images/icon/rexiao.png" alt="" /></div>
				<a href="#">更多 >></a>
			</div>
			<div class="noticeGoods">
				<ul>
					<li v-for="i in goodsItem">
						<img :src="i.src"/>
						<p class="noticeTitle">{{i.title}}</p>
						<div class="noticeInfo">
							<p>券后价：￥<span>39.9</span></p>
							<p>优惠券：￥<span>100</span></p>
						</div>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: 'notice',
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
				]
			}
		}
	}
</script>

<style lang="scss">
	.noticeBox{
		margin-top: 16px;
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
		.noticeGoods{
			margin: 0 16px;
			height: 600px;
			/*background: #ccc;*/
			ul{
				height: 100%;
				
				li{
					width: 160px;
					float: left;
					margin-right: 8px;
					img{
						width: 100%;
					}
				}
			}
		}
	}
</style>
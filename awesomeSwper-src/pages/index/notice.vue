<template>
	<div id="notice">
		<div class="noticeBox">
			<div class="goodsClass">
				<div class="hotBuy">明日预告<img src="../../assets/images/icon/rexiao.png" alt="" /></div>
				<a href="#">更多 >></a>
			</div>
			<div class="noticeGoods">
				<ul>
					<li v-for="(i,index) in goodsItem">
						<img :src="i.ImgUrl"/>
						<p class="noticeTitle">{{i.GoodsName}}</p>
						<div class="noticeInfo">
							<p>券后价：<i>￥</i><span>{{i.LastPrice}}</span></p>
							<p>优惠券：<i>￥</i><span>{{i.ActMoney}}</span></p>
						</div>
						<div class="remainingTime">
							<p>00:00:00后开始</p>
						</div>
						<div class="showNum">
							<p>优惠券剩余：<span>{{i.Coupon_SaleCount}}</span></p>
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
				currentIndex: '',
				goodsItem: []
//				goodsItem: [
//					{id: 1, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 2, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 3, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 4, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 5, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 6, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 7, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 8, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 9, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 10, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 11, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 12, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 13, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 14, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'}
//				]
			}
		},
		created() {
			this.$axios({
				method: 'GET',
				url: 'http://api.xuandan.com/DataApi/HotGoods?AppKey=hveo9k3frc&type=2&page=1',
			}).then(function(res){
				var data = res.data.data
				this.goodsItem = data.slice(0,14)
//				console.log(this.goodsItem)
			}.bind(this)).catch(function(err){
				console.log(err)
			})
			this.getTime()
		},
		methods: {
			getTime(){
				var date = new Date()
				var nowTime = date.getTime();
				var newTime = Date.parse(new Date('2018-12-17 00:00:00'));
				var difference = newTime - nowTime
//				this.timestampToTime(difference);
				
				console.log(this.timestampToTime(difference))
			},
			timestampToTime(timestamp) {
		        var date = new Date(timestamp * 100000);//时间戳为10位需*1000，时间戳为13位的话不需乘1000
		        var h = date.getHours() + ':';
		        var m = date.getMinutes() + ':';
		        var s = date.getSeconds();
		        return h+m+s;
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
			margin: 8px 16px;
			height: 602px;
			/*background: #ccc;*/
			ul{
				height: 100%;
				overflow: hidden;
				li{
					width: 158px;
					height: 270px;
					float: left;
					border: 1px solid #fff;
					margin-right: 8px;
					margin-top: 8px;
					position: relative;
					img{
						width: 100%;
						cursor: pointer;	
					}
					.noticeTitle{
						height: 38px;
						color: #333;
						font-size: 14px;
						overflow: hidden;
					}
					.noticeTitle:hover{
						cursor: pointer;
						color: #ff4141;
						text-decoration: underline;
						
					}
					.noticeInfo{
						margin: 4px 0 0 8px;
						p{
							font-size: 12px;
							color: #999;
						}
					}
					.remainingTime{
						text-align: center;
						line-height: 31px;
						background: #ccc;
						margin-top: 4px;
						color: #333;
					}
					.showNum{
						position: absolute;
						z-index: 9999;
						width: 158px;
						height: 40px;
						border: 1px solid #f00;
						/*box-shadow: 0 0 4px red;*/
						border-top: 0;
						background: #fff;
						text-align: center;
						display: none;
						margin-left: -1px;
						p{
							font-size: 14px;
							color: #333;
							line-height: 40px;
							span{
								color: #ff4141;
							}
						}
					}
				}
				li:hover{
					border: 1px solid #f00;
					/*box-shadow: 0 0 4px red*/
				}
				li:hover .showNum{
					display: block;
				}
			}
		}
	}
	
</style>
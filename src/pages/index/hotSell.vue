<template>
	<div id="hotSell">
		<div class="goodsClass">
			<div class="hotBuy">热销产品<img src="../../assets/images/icon/rexiao.png" alt="" /></div>
			<a href="#">更多 >></a>
		</div>
		<div class="hotSellBox">
			<div class="itemLeft">
				<div class="imgItem" v-for="(good,index) in leftBigGood">
					<div class="imgDetail" :class="{position: index===1}">
						<img :src="good.ImgUrl"/>
						<div class="markP"></div>
						<a :href="good.GoodsLink"><p class="detailEntry">点击查看详情</p></a>
					</div>
				</div>
				<!--<div class="imgItem ">
					<div class="imgDetail position">
						<img src="../../../static/product.jpg"/>
						<div class="markP"></div>
						<p class="detailEntry">点击查看详情</p>
					</div>
				</div>-->
			</div>
			<div class="itemRight">
				<ul>
					<li 
						class="hotSellGoods"
						v-for="i in goodslist"
					>
						<img :src="i.ImgUrl"/>
						<p>{{i.GoodsName}}</p>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
	export default{
		name: 'hotSell',
		data(){
			return{
				goodslist: [],
				leftBigGood: []
//				goodslist: [
//					{id: 1, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 2, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 3, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 4, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 5, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 6, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'},
//					{id: 7, src: '../../static/product.jpg', title: '大叔家长靴女过膝欧美2018新款秋冬粗跟弹力瘦瘦靴中跟显瘦长筒靴', price: '688.00', coupon: '200', lastPrice: '186.00'}
//				]
			}
		},
		created(){
//			this.newGoods = this.newGoods.concat(this.addGoods)
			this.$axios({
				method: 'GET',
				url: 'http://api.xuandan.com/DataApi/index?AppKey=hveo9k3frc&type=6',
			}).then(function(res){
				var data = res.data.data
				this.goodslist = data.slice(2,17)
				this.leftBigGood = data.slice(0,2)
//				console.log(this.leftBigGood)
			}.bind(this)).catch(function(err){
				console.log(err)
			})
		}
	}
</script>

<style lang="scss">
	#hotSell{
		background: #fff;
		margin-top: 16px;
		height: 670px;
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
		.hotSellBox{
			margin: 16px 16px 0 16px;
			margin-left: 16px;
			.itemLeft{
				width: 28%;
				height: 622px;
				float: left;
				border-right: 3px dashed #ccc;
				.imgItem{
					position: relative;
					margin-bottom: 8px;
					.position{
						top: 308px;
					}
					.imgDetail{
						width: 300px;
						height: 300px;
						position: absolute;
						img{
							width: 100%;
							height: 100%;
							cursor: pointer;
						}
						.markP{
							width: 100%;
							height: 30px;
							position: absolute;
							bottom: 0;
							left: 0;
							opacity:0.5;
							box-shadow: 0 -1px 3px #000;
							background: #ccc;
						}
						.detailEntry{
							position: absolute;
							bottom: 0;
							left: 0;
							line-height: 30px;
							margin-left: 16px;
							font-size: 16px;
							color: #333;
							cursor: pointer;
						}
						.detailEntry:hover{
							text-decoration: underline;
							color: #ff4141;
						}
					}
					.imgDetail:hover{
						width: 310px;
						height: 310px;
						z-index: 999;
						border: 1px solid #f00;
						box-shadow:0 0 6px #f00 ;
					}
				}
			}
			.itemRight{
				width: 70%;
				height: 616px;
				float: left;
				margin-left: 16px;
				/*background: #ccc;*/
				ul{
					height: 100%;
					li{
						width: 160px;
						height: 201px;
						float: left;
						margin-right: 3px;
						margin-bottom: 4px;
						border: 1px solid #fff;						
						background: #fff;
						img{
							width: 100%;
							height: 80%;
							cursor: pointer;
						}
						p{
							font-size: 14px;
							cursor: pointer;
							height: 22px;
							line-height: 30px;
							white-space: nowrap;
							text-overflow: ellipsis;
							overflow: hidden;
							color: #333;
						}
						p:hover{
							text-decoration: underline;
							color: #ff4141;
						}
					}
					li:hover{
						border: 1px solid #f00;
						box-shadow:0 0 6px #f00 ;
					}
				}
			}
		}
	}
</style>
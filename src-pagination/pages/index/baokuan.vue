<template>
	<div id="baokuan">
		<div class="bodyBox">
			<div class="goodsClass">
				<div class="hotBuy">爆款<img src="../../assets/images/icon/rexiao.png" alt="" /></div>
				<a href="#">更多 >></a>
			</div>
			<div class="goodsWrapper" ref="wrapper">
				<ul class="goodsContent">
					<li v-for="item in goodsItem" :key="item.id">
						<img class="goodsImg" :src="item.ImgUrl"/>
						<div class="curtailInfo">
							<p class="goodsTitle"><a href=":;javascript">{{item.GoodsName}}</a></p>
							<div class="goodsPrice">
								<div class="LastPriceBox">
									<img src="../../assets/images/icon/quanhoujia.png"/>
									<p class="goodsLastPrice">￥<span>{{item.LastPrice}}</span></p>
								</div>
								<p class="goodsBeforPrice">原价：￥<span>{{item.GoodsPrice}}</span></p>
							</div>
						</div>
						<!--优惠券图片-->
						<div class="yhqbg">
							<a class="jumpOutside" target="_blank" :href="item.ActLink"><p class="yhPrice">{{item.ActMoney}}</p></a>
						</div>
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
	import BScroll from 'better-scroll' 
	
	export default{
		name: 'baokuan',
		data(){
			return {
				goodsItem: []
			}
		},
		created() {
			this.$axios({
				method: 'GET',
				url: 'http://api.xuandan.com/DataApi/PyqGoods?AppKey=hveo9k3frc&type=2',
			}).then(function(res){
				var data = res.data.data
				this.goodsItem = data.slice(0,10)
//				console.log(this.goodsItem)
			}.bind(this)).catch(function(err){
				console.log(err)
			})
		},
		mounted() {
//		    this.getSingerData()
			this.$nextTick(() => {
		        let bscrollDom = this.$refs.wrapper;
		        this.aBscroll = new BScroll(bscrollDom,{
		        	click: true,
		        	scrollX: true
		        })
		    })
		}
	}
</script>

<style>
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
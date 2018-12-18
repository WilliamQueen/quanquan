<template>
	<div class="womenBox">
		<div class="womensWearGoods">
			<ul>
				<li v-for="(i,index) in goodsItem">
					<div class="imgWrap">
						<a :href="i.GoodsLink"  target="_blank">
							<img :src="i.ImgUrl"/>
						</a>
					</div>
					<p class="noticeTitle">
						<a :href="i.GoodsLink"  target="_blank">
							{{i.GoodsName}}
						</a>
					</p>
					<div class="noticeInfo">
						<p>券后价：<i>￥</i><span>{{i.LastPrice}}</span></p>
						<!--优惠券图片-->
						<div class="yhqbg">
							<a class="jumpOutside" target="_blank" :href="i.ActLink"><p class="yhPrice">{{i.ActMoney}}</p></a>
						</div>
					</div>
					<div class="shop">
						<a href="#">
							<img src="../../../static/icon/shop.png"/>
							<span>{{i.ShopName}}</span>
						</a>
					</div>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
	export default{
		name: 'women',
		data(){
			return{
				goodsItem: []
			}
		},
		created() {
			this.$axios({
				method: 'GET',
				url: 'http://api.xuandan.com/DataApi/index?AppKey=hveo9k3frc&page=1&cid=1',
			}).then(function(res){
				var data = res.data.data
				this.goodsItem = data
				console.log(this.goodsItem)
			}.bind(this)).catch(function(err){
				console.log(err)
			})
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.womenBox{
		width: 1190px;
		height: 100%;
		margin: 0 auto;
	}
	.womensWearGoods{
		margin: 8px 16px 16px;
		ul{
			height: 100%;
			overflow: hidden;
			li{
				width: 221px;
				height: 374px;
				float: left;
				border: 1px solid #fff;
				margin-right: 8px;
				margin-top: 8px;
				position: relative;
				background: #fff;
				.imgWrap{
					width: 100%;
					height: 226px;
					img{
						max-width: 226px;
						max-height: 226px;
						cursor: pointer;	
					}
				}
				.noticeTitle{
					height: 20px;
					color: #333;
					margin-left: 8px;
					font-size: 14px;
					text-overflow: ellipsis;
		 			white-space: nowrap;
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
						font-size: 14px;
						color: #333;
						i{
							color: #f00;
						}
						span{
							font-size: 24px;
							color: #f00;
						}
					}
					.yhqbg{
						width: 130px;
						height: 44px;
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
								width: 40px;
								text-align: center;
								font-size: 24px;
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
				.shop{
					height: 30px;
					line-height: 30px;
					margin-left: 8px;
					a{
						color: #888;
						font-size: 12px;
						img{
							vertical-align: middle;
						}
					}
				}
			}
			li:hover{
				border: 1px solid #f00;
				/*box-shadow: 0 0 4px red*/
			}
		}
	}
</style>
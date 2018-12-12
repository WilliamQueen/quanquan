<template>
	<div id="hotSell">
		<div class="goodsClass">
			<div class="hotBuy">热销产品<img src="../../assets/images/icon/rexiao.png" alt="" /></div>
			<a href="#">更多 >></a>
		</div>
		<div class="hotSellBox">
			<div class="itemLeft">
				<div class="imgItem">
					<div class="imgDetail">
						<img src="../../../static/product.jpg"/>
						<div class="markP"></div>
						<p class="detailEntry">点击查看详情</p>
					</div>
				</div>
				<div class="imgItem ">
					<div class="imgDetail position">
						<img src="../../../static/product.jpg"/>
						<div class="markP"></div>
						<p class="detailEntry">点击查看详情</p>
					</div>
				</div>
			</div>
			<div class="itemRight">
				
			</div>
		</div>
		<div style="height: 200px;">
			
		</div>
	</div>
</template>

<script>
	export default{
		name: 'hotSell'
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
				width: 332px;
				height: 622px;
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
							color: #ff4141;
							cursor: pointer;
						}
						.detailEntry:hover{
							text-decoration: underline;
						}
					}
					.imgDetail:hover{
						width: 310px;
						height: 310px;
						border-radius: 2px;
						z-index: 999;
						box-shadow:0 0 6px #f00 ;
					}
				}
			}
		}
	}
</style>
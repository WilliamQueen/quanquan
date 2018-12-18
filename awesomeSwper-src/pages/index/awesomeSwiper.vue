<template>
	<div class="awesomeSwiper">
		<swiper :options="swiperOption">
			<swiper-slide><div class="box1"></div></swiper-slide>
			<swiper-slide><div class="box2"></div></swiper-slide>
			<swiper-slide><div class="box3"></div></swiper-slide>
		</swiper>
		<div class="swiper-pagination "  slot="pagination"></div>
      	<div class="swiper-button-prev swiper-button-black" slot="button-prev"></div>
      	<div class="swiper-button-next swiper-button-black" slot="button-next"></div>
	</div>
</template>

<script>
	import { swiper, swiperSlide } from 'vue-awesome-swiper'  
	export default{
		name: 'awesomeSwiper',
		components: {
			swiper,
			swiperSlide
		},
		data() {
			return {
				swiperOption: {
					autoplay: true,
					loop:true,
//					autoplay: {
//					    delay: 100, //自动切换的时间间隔，单位ms
//					    stopOnLastSlide: false, //当切换到最后一个slide时停止自动切换
//					    stopOnLastSlide: true, //如果设置为true，当切换到最后一个slide时停止自动切换。
//					    disableOnInteraction: true, //用户操作swiper之后，是否禁止autoplay。
//					    reverseDirection: true, //开启反向自动轮播。
//					    waitForTransition: true, //等待过渡完毕。自动切换会在slide过渡完毕后才开始计时。
//					},
      				speed: 1000,
					 navigation: {
			              nextEl: '.swiper-button-next',
			              prevEl: '.swiper-button-prev',
			          },
			          //分页器设置         
			          pagination: {
			              el: '.swiper-pagination',
			              clickable :true
			          }
		        }
			}
		}
	}
</script>

<style lang="scss">
	.box1{
		width: 100%;
		height: 300px;
		background: #26A2FF;
	}
	.box2{
		width: 100%;
		height: 300px;
		background: #2C3E50;
	}
	.box3{
		width: 100%;
		height: 300px;
		background: #5CADAD;
	}
</style>
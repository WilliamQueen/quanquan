<template>
	<div id="back">
		<transition name="fade">
			<div class="toTop" v-if="isShow">
					<div class="bgImg" @click="toTop"></div>
			</div>
		</transition>
	</div>
</template>

<script>
	export default{
		name: 'backTop',
		data(){
			return{
				isShow: false,
				show: true
			}
		},
		methods: {
			toTop(){
				document.documentElement.scrollTop = document.body.scrollTop = 0
			}
		},
		created(){
			window.addEventListener('scroll',function(){
				var scrollTop = document.documentElement.scrollTop;
				if(scrollTop > 300){
					this.isShow = true
//					console.log(this)
				}else{
					this.isShow = false
				}
//				console.log(document.documentElement.scrollTop)
			}.bind(this))
		}
	}
</script>

<style lang="scss">
	.toTop{
		width: 50px;
		height: 50px;
		border: 1px solid #ccc;
		position: fixed;
		right: 24px;
		bottom: 60px;
		display: flex;
		justify-content: center;
		align-items: center;
		background: #fff;
		.bgImg{
			width: 26px;
			height: 26px;
			background: url(../../static/icon/back.png);
			background-size: 100%;
		}
	}
	.toTop:hover{
		cursor: pointer;
		background: #ccc;
	}
	.toTop:hover .bgImg{
		background: url(../../static/icon/back-act.png);
		background-size: 100%;
	}
	.fade-enter-active, .fade-leave-active {
	  transition: opacity .5s;
	}
	.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
	  opacity: 0;
	}
</style>
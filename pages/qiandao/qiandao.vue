<template>
	<div>
		
		<!-- 签退按钮 -->
		<div class="signBackBtn white pubBj center flexColumn" @click="timeShow">
			<p class="fs18 mgb10">签到</p>
			<p class="fs14">08:02:13</p>
		</div>
		<div class="pdlr4 flexCenter qianTime center fs12" v-show="is_show">
			<div class="flexColumn">
				<span class="time">09:02</span>
				<p class="fs14">签到</p>
			</div>
			<span class="xian mglr15"></span>
			<div class="flexColumn">
				<span class="time">18:02</span>
				<p class="fs14">签退</p>
			</div>
		</div>
		
	</div>
</template>


<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				is_show:false,
				neituiDate:[{},{},{}]
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			timeShow(){
				const self = this;
				self.is_show = true
			},
			getMainData() {
				const self = this;
				const postData = {};
				postData.tokenFuncName = 'getProjectToken';
				var callback = function(res){
				    console.log('getMainData', res);
				    self.mainData.push.apply(self.mainData,res.info.data);		        
				};
				self.$apis.orderGet(postData, callback);
			}
		},
	}
</script>


<style>
	@import "../../assets/style/public.css";
	@import "../../assets/style/navbar.css";
	
	/* 签退按钮 */
	.signBackBtn{width: 120px; height: 120px; border-radius: 50%;margin: 50px auto;box-shadow: 0 2px 10px rgba(0, 70, 158, 0.6);}
	
	.qianTime .time{width: 45px;height: 45px; line-height: 45px;border-radius: 50%;border: 1px solid #e1e1e1;margin-bottom: 5px;}
	.qianTime .xian{width: 100px;height: 1px;background: #e1e1e1;margin-bottom: 26px;}
	
	
</style>


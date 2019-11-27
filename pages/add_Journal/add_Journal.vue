<template>
	<div>
		
		<div class="pdlr4">
			<div class="pdtb15 bordB1 color9 fs13">请写下你这段时间的工作内容</div>
			<div>
				<textarea rows="" cols="" placeholder="记录工作内容..."></textarea>
			</div>
		</div>
		
		<div class="submitbtn" style="margin-top: 80px;">
			<button class="btn" @click="Router.navigateTo({route:{path:'/pages/index/index'}})">提交</button>
		</div>
		
	</div>
</template>


<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				is_show:false
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
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
	
	textarea{width: 100%;height: 150px; padding: 10px 0; box-sizing: border-box;border: none; font-size: 12px;}	
	
</style>


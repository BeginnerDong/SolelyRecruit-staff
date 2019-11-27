<template>
	<div>
		
		<div class="editLine pdlr4">
			<ul>
				<li class="flexRowBetween">
					<span class="flex title"><em class="red">*</em>缘由</span>
					<div class="rr pr oneAdrs flexRowBetween">
						<input type="text" placeholder="" value="">
						<img class="arrowR" src="images/togo-out-icon1.png" >
					</div>
				</li>
				<li class="flexRowBetween">
					<span class="flex title"><em class=""></em>备注</span>
					<div class="rr">
						<textarea rows="" cols="" placeholder="请填写备注信息"></textarea>
					</div>
				</li>
			</ul>
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
	@import "../../assets/style/editInput.css";
	
	
</style>


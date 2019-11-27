<template>
	<div>
		
		<div class="editLine pdlr4">
			<ul>
				<li class="flexRowBetween">
					<span class="flex title"><em class="red">*</em>地点</span>
					<div class="rr pr oneAdrs flexRowBetween">
						<input type="text" placeholder="" value="">
						<img class="arrowR" src="../../static/images/togo-out-icon1.png" >
					</div>
				</li>
				<li class="flexRowBetween">
					<span class="flex title"><em class=""></em>备注</span>
					<div class="rr">
						<textarea rows="" cols="" placeholder="请填写备注信息"></textarea>
					</div>
				</li>
				<li class="flexRowBetween">
					<span class="flex title" style="width: 23%;"><em class="red">*</em>拍照上传</span>
					<div class="rr picLis flex" style="width: 77%;">
						<div class="item">
							<img class="pic" src="../../static/images/togo-out-img.png" >
						</div>
						<div class="item pr">
							<input class="upload" type="file" name="" value="" />
							<img class="pic" src="../../static/images/togo-out-icon.png" >
						</div>
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


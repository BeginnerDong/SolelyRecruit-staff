<template>
	<div>
		
		<div class="editLine pdlr4">
			<ul>
				<li class="flexRowBetween">
					<span class="flex title"><em class="red">*</em>请假事由</span>
					<div class="rr">
						<textarea rows="" cols="" placeholder="" value=""></textarea>
					</div>
				</li>
				<li class="flexRowBetween">
					<span class="flex title"><em class="red">*</em>请假类型</span>
					<div class="rr">
						<div class="w175">
							<select>
								<option value ="volvo">事假</option>
								<option value ="saab">病假</option>
								<option value="opel">婚假</option>
							</select>
						</div>
					</div>
				</li>
				<li class="flexRowBetween">
					<span class="flex title"><em class="red">*</em>起止时间</span>
					<div class="rr">
						<div class="w175">
							<input type="datetime" name="" value="" />
						</div>
					</div>
				</li>
				<li class="flexRowBetween">
					<span class="flex title"><em class="red"></em>&nbsp;</span>
					<div class="rr">
						<div class="w175">
							<input type="datetime" name=""  value="" />
						</div>
					</div>
				</li>
				<li class="flexRowBetween">
					<span class="flex title"><em class="red">*</em>时长(小时)</span>
					<div class="rr">
						<div class="w175">
							<input type="number" name="" value="" />
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
	
	.editLine li .title{width: 26%;line-height: 30px;}
	select{height: 30px; line-height: 30px;width: 100%;border: 1px solid #eee;padding: 0 5px;box-sizing: border-box;}
	.editLine li .w175{width: 175px;}
	.editLine li .w175 input{ width: 100%; line-height: 30px;height: 30px;display: block;box-sizing: border-box;padding: 0 5px;border:1px solid #eee;}
	
</style>


<template>
	<div>
		
		<div class="editLine pdlr4 fs13 pdb15"  v-for="(item,index) in leaveDate" :key="index">
			<h1 class="ftw fs14 pdt20">19年10月24日10点24分</h1>
			<ul>
				<li class="flexRowBetween">
					<span class="title">请假原因</span>
					<div class="rr">朋友结婚</div>
				</li>
				<li class="flexRowBetween">
					<span class="title">请假类型</span>
					<div class="rr">事假</div>
				</li>
				<li class="flexRowBetween">
					<span class="title">起止时间</span>
					<div class="rr">2019.11.09-2019.11.10</div>
				</li>
				<li class="flexRowBetween">
					<span class="title">时长(小时)</span>
					<div class="rr">24小时</div>
				</li>
			</ul>
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
				leaveDate:[{},{}]
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
		}
	}
</script>


<style>
	@import "../../assets/style/public.css";
	@import "../../assets/style/editInput.css";
	page{padding-bottom: 40px;}
	.editLine{border-bottom: 10px solid #f5f5f5;}
	.editLine:last-child{border-bottom: none;}
	.editLine li{margin-top: 15px;}
	.editLine li .title{line-height: initial; width: 25%;}
	.editLine li .rr{color: #666;}
</style>


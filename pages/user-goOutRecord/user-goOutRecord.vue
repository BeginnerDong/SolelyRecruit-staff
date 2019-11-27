<template>
	<div>
		
		<div class="editLine pdlr4 fs13 pdb10" v-for="(item,index) in goOutDate" :key="index">
			<ul>
				<li class="flexRowBetween">
					<span class="title">时间</span>
					<div class="rr">2019.11-08</div>
				</li>
				<li class="flexRowBetween">
					<span class="title">地点</span>
					<div class="rr">西安市高新区大都荟20层</div>
				</li>
				<li class="flexRowBetween">
					<span class="title">缘由</span>
					<div class="rr">见客户</div>
				</li>
				<li class="flexRowBetween">
					<span class="title">备注</span>
					<div class="rr">活动时间备注法定假森林防火后尽快刚发的附加费后</div>
				</li>
				<li class="flexRowBetween">
					<span class="flex title" style="width: 23%;">拍照上传</span>
					<div class="rr picLis flex" style="width: 77%;">
						<div class="item">
							<img class="pic" src="../../static/images/togo-out-img.png" >
						</div>
					</div>
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
				goOutDate:[{},{}]
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
	.editLine{border-bottom: 10px solid #f5f5f5;}
	.editLine:last-child{border-bottom: none;}
	.editLine li{margin-top: 15px;}	
	.editLine li .title{line-height: initial;}
	.editLine li .rr{color: #666;}
	
</style>


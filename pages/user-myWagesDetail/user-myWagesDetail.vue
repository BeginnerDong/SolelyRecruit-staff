<template>
	<div>
		
		<div class="userInfor pdlr4 fs13">
			<ul>
				<li>
					<span class="ll">姓名</span>
					<div class="rr color6">张思淼</div>
				</li>
				<li>
					<span class="ll">职位</span>
					<div class="rr color6">会计助理</div>
				</li>
				<li>
					<span class="ll">底薪</span>
					<div class="rr color6">1696.00</div>
				</li>
				<li>
					<span class="ll">绩效</span>
					<div class="rr color6">4664.00</div>
				</li>
				<li>
					<span class="ll">基本绩效</span>
					<div class="rr color6">7000.00</div>
				</li>
				<li>
					<span class="ll">奖励金额</span>
					<div class="rr color6">0.00</div>
				</li>
				<li>
					<span class="ll">扣除金额</span>
					<div class="rr color6">-56.22</div>
				</li>
				<li>
					<span class="ll">绩效扣除</span>
					<div class="rr color6">-0.00</div>
				</li>
				<li>
					<span class="ll">绩效奖励</span>
					<div class="rr color6">-0.00</div>
				</li>
				<li>
					<span class="ll">总计</span>
					<div class="rr price">7000.00</div>
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
		}
	}
</script>


<style>
	@import "../../assets/style/public.css";
	@import "../../assets/style/userInfor.css";
	
	.userInfor li .ll{width: 20%;}
	.userInfor li .rr{width: 80%;}
</style>


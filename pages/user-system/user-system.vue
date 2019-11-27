<template>
	<div>
		
		<!-- 日志制度 -->
		<div class="pdlr4">
			<h1 class="fs16 pdt15">日志制度</h1>
			<div class="xqInfor pdtb10">
				<div class="cont fs13">
					<p>1、超过噶几了价格拉上将公开发多少价格夫人就开始联合国就看见发</p>
					<p>2、能处理好对账、开票、销售回款、账龄分析等业务，能独立制作销售周报、月报工作。</p>
					<p>2、能处理好对账、开票、销售回款、账龄分析等业务，能独立制作销售周报、月报工作。</p>
				</div>
			</div>
		</div>
		<div class="f5H10"></div>
		
		<!-- 请假制度 -->
		<div class="pdlr4">
			<h1 class="fs16 pdt15">请假制度</h1>
			<div class="xqInfor pdtb10">
				<div class="cont fs13">
					<p>1、超过噶几了价格拉上将公开发多少价格夫人就开始联合国就看见发</p>
					<p>2、能处理好对账、开票、销售回款、账龄分析等业务，能独立制作销售周报、月报工作。</p>
					<p>2、能处理好对账、开票、销售回款、账龄分析等业务，能独立制作销售周报、月报工作。</p>
				</div>
			</div>
		</div>
		<div class="f5H10"></div>
		
		<!-- 考勤制度 -->
		<div class="pdlr4">
			<h1 class="fs16 pdt15">考勤制度</h1>
			<div class="xqInfor pdtb10">
				<div class="cont fs13">
					<p>1、超过噶几了价格拉上将公开发多少价格夫人就开始联合国就看见发</p>
					<p>2、能处理好对账、开票、销售回款、账龄分析等业务，能独立制作销售周报、月报工作。</p>
					<p>2、能处理好对账、开票、销售回款、账龄分析等业务，能独立制作销售周报、月报工作。</p>
				</div>
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
	@import "../../assets/style/prodctDetail.css";
	page{padding-bottom:50px;}
</style>


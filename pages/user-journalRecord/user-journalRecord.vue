<template>
	<div>
		
		<div class="flexCenter myWagesTit pdtb20">
			<img class="icon" src="../../static/images/arrow-icon.png" >
			<h2 class="tt pdlr10">2019年11月08日</h2>
			<img class="icon" src="../../static/images/arrow-icon1.png" >
		</div>
		
		<div class="pdlr4">
			<div class="journalList whiteBj radius8 pd15 fs12 mgb15">
				<ul>
					<li class="" v-for="child in journaDate">
						<p class="text">好几个发生过黄金矿工打哈萨克复合大师好几个客户范德萨发如果</p>
						<span class="time flexEnd color6">16:06:20</span>
					</li>
				</ul>
				<div class="flexEnd fs13 pubColor pdt5">2019年11月08日</div>
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
				journaDate:[{},{},{}]
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
	page{background: #F5F5F5;padding-bottom: 40px;}
	.myWagesTit .icon{width: 6px; height: 12px; display: block;margin: 0 5px;}
	.journalList li{padding-bottom: 15px; align-items: flex-start;}
</style>


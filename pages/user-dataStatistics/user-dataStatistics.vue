<template>
	<div>
		
		<div class="flexCenter myWagesTit pdtb20">
			<img class="icon" src="../../static/images/arrow-icon.png" >
			<h2 class="tt pdlr10 ftw">2019年11月08日</h2>
			<img class="icon" src="../../static/images/arrow-icon1.png" >
		</div>
		
		<div class="dataCont flex white fs12">
			<div class="item flexColumn one ">
				<p class="num">1</p>
				<p class="name">请假</p>
			</div>
			<div class="item flexColumn two ">
				<p class="num">5</p>
				<p class="name">迟到</p>
			</div>
			<div class="item flexColumn three">
				<p class="num">4</p>
				<p class="name">内推</p>
			</div>
			<div class="item flexColumn four">
				<p class="num">10</p>
				<p class="name">外出</p>
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
				rewardDate:[{},{},{}]
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
	
	.myWagesTit .icon{width: 6px; height: 12px; display: block;margin: 0 5px;}
	.dataCont{width: 200px; height: 200px; flex-wrap: wrap;margin: 60px auto 20px auto;}
	.dataCont .item{width:100px; height: 100px;box-sizing: border-box;padding:0 10px;}
	.dataCont .item.one{background: url(../../static/images/data-statistics-icon1.png)no-repeat 0 0/100% 100%;padding: 15px 0 0 15px;}
	.dataCont .item.two{background: url(../../static/images/data-statistics-icon2.png)no-repeat 0 0/100% 100%;padding: 15px 15px 0 0;}
	.dataCont .item.three{background: url(../../static/images/data-statistics-icon.png)no-repeat 0 0/100% 100%;padding: 0 0 15px 15px;}
	.dataCont .item.four{background: url(../../static/images/data-statistics-icon3.png)no-repeat 0 0/100% 100%;padding: 0 15px 15px 0;}
	.dataCont .item .num{font-size: 16px;margin-bottom:5px;}
	
</style>


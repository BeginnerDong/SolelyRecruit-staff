<template>
	<div>
		
		<div class="flexCenter myWagesTit pdtb20">
			<div class="fs12 color9 flex"><img class="icon" src="../../static/images/arrow-icon.png"/>上月</div>
			
			<h2 class="tt pdlr20 mglr10 ftw fs14">2019年11月</h2>
			<div class="fs12 color9 flex">下月<img class="icon" src="../../static/images/arrow-icon1.png"/></div>
		</div>
		
		<div class="calendar-layer">
			<div class="day-title pdlr4 flexRowBetween">
				<span class="dd">日</span>
				<span class="dd">一</span>
				<span class="dd">二</span>
				<span class="dd">三</span>
				<span class="dd">四</span>
				<span class="dd">五</span>
				<span class="dd">六</span>
			</div>
			<div class="pdlr4 dayCont flex">
				<div class="item flexColumn color9 fs12"  v-for="(item,index) in dayData" :key="index">
					<span class="color2 fs14 day">{{item}}</span>
					<span>08:23:21</span>
					<span class="xian"></span>
					<span>19:12:23</span>
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
				is_show:false,
				currDay:0,
				dayData:31
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
	.day-title{line-height: 30px;background: #ecf6ff;padding: 0 2%;}
	.day-title .dd{width: 14.2%; text-align: center;}
	.dayCont{flex-wrap: wrap;padding: 0 2%;}
	.dayCont .item{width: 14.2%; text-align: center;padding:15px 0; line-height: 14px;font-size: 8px;border-bottom: 1px solid #eee;}
	.dayCont .item .day{margin-bottom: 8px;line-height: 18px;}
	.dayCont .item .xian{ width: 1px; height: 8px;background: #ccc; margin: 3px auto; display: block;}
</style>


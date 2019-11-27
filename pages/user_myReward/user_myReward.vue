<template>
	<div>
		
		<div class="myExtendTop white pr">
			<div class="bigNum">500<em class="fs12">元</em></div>
			<div class="yuan pdt5 pdb15 fs14">总奖励</div>
			<div class="txBtn fs12"  @click="Router.navigateTo({route:{path:'/pages/user_myCashOut/user_myCashOut'}})">提现</div>
			<div class="rewarddata white fs12">
				<ul class="flexRowBetween">
					<li class="item flexColumn">
						<p class="num">200</p>
						<p class="text">投递</p>
					</li>
					<li class="item flexColumn">
						<p class="num">100</p>
						<p class="text">面试</p>
					</li>
					<li class="item flexColumn">
						<p class="num">200</p>
						<p class="text">入职</p>
					</li>
				</ul>
			</div>
		</div>
		
		<div class="myRowBetween pdlr4" >
			<div class="item flexRowBetween" v-for="item in rewardDate">
				<div class="left flex">
					<img class="photo" src="../../static/images/push-img.png" >
					<div class="infor">
						<h1 class="ftn avoidOverflow">张婷&nbsp;·&nbsp;<em class="pubColor">会计助理</em></h1>
						<div class="phone mgt5 fs13 color9">1568985232</div>
					</div>
				</div>
				<div class="right fs12">
					<p class="ftr mgb5">状态：已投递</p>
					<p class="ftr">奖励：<em class="red fs13">20</em></p>
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
	/* 我的收益 */
	.myExtendTop{width: 100%; text-align: center;box-sizing: border-box;padding: 20px 4%; background: #398EF9;}
	.myExtendTop .bigNum{font-size: 40px; padding: 0 4%; line-height:40px;}
	.myExtendTop .txBtn{ width: 50px; height: 24px;line-height: 24px; background: #fff; color: #398EF9; border-radius: 20px;  display: block;position: absolute; top: 20px;right: 10px;}
	
	.rewarddata .item{width: 33.3%;position: relative;}
	.rewarddata .item .num{font-size: 14px;margin-bottom: 3px;}
	.rewarddata .item:after{content: ''; width: 0px; height: 25px;border-right: 1px dashed #fff;position: absolute;right: 0;top: 50%;transform: translateY(-50%);}
	.rewarddata .item:last-child:after{display: none;}
	/* 信息RowBetween */
	.myRowBetween .item{ padding: 15px 0;border-bottom: 1px solid #eee;background: #fff;}
	.myRowBetween .item .left{width: 75%;}
	.myRowBetween .item .left .photo{width: 50px; height: 50px; display: block;margin-right: 5px;}
	.myRowBetween .item .left .infor{width: 75%;}
	.myRowBetween .item .right{width: 25%;}
	
</style>


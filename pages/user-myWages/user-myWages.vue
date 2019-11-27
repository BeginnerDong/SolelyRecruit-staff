<template>
	<div>
		
		<div class="flexCenter myWagesTit pdtb20">
			<img class="icon" src="../../static/images/arrow-icon.png" >
			<h2 class="tt pdlr10 ftw">2019年</h2>
			<img class="icon" src="../../static/images/arrow-icon1.png" >
		</div>
		
		<div class="myWagesMX fs14 mglr4 whiteBj radius8">
			<ul class="flex">
				<li class="flexColumn" v-for="(item,index) in wagesDate" :key="index" @click="Router.navigateTo({route:{path:'/pages/user-myWagesDetail/user-myWagesDetail'}})">
					<p class="month">{{item.month}}</p>
					<p class="money">{{item.money}}</p>
				</li>
			</ul>
		</div>
		<div class="pdlr4 mgtb20 ftw center">2019年累计工资总额：123350</div>
		
	</div>
</template>


<script>
	export default {
		data() {
			return {
				Router:this.$Router,
				showView: false,
				is_show:false,
				wagesDate:[
					{month:'1月',money:'5600'},
					{month:'2月',money:'5600'},
					{month:'3月',money:'5600'},
					{month:'4月',money:'5600'},
					{month:'5月',money:'5600'},
					{month:'6月',money:'5600'},
					{month:'7月',money:'5600'},
					{month:'8月',money:'5600'},
					{month:'9月',money:'5600'},
					{month:'10月',money:'5600'},
					{month:'11月',money:'5600'},
					{month:'12月',money:'5600'}
				]
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
	
	page{background: #F5F5F5;}
	.myWagesTit .icon{width: 6px; height: 12px; display: block;margin: 0 5px;}
	
	.myWagesMX ul{flex-wrap: wrap;}
	.myWagesMX li{width: 33.3%;height: 72px;border-right: 1px solid #eee;border-bottom: 1px solid #eee;box-sizing: border-box;}
	.myWagesMX li a{width: 100%; height: 100%;}
	.myWagesMX li .money{color: #FF3B3B;padding-top: 3px;}
	.myWagesMX li:nth-of-type(3n){border-right: none;}
</style>


<template>
	<div>
		
		<div class="userHead flexRowBetween">
			<div class="ll">
				<h1 class="fs22 mgb15">张望</h1>
				<p>余额：520</p>
			</div>
			<div class="flexEnd">
				<img class="Rphoto" src="../../static/images/push-img.png"/>
			</div>
		</div>
		
		<div class="userdata pdtb10">
			<ul class="flexRowBetween">
				<li class="item flexColumn">
					<h3 class="num">10</h3>
					<p class="text">内推</p>
				</li>
				<li class="item flexColumn">
					<h3 class="num">6</h3>
					<p class="text">迟到</p>
				</li>
				<li class="item flexColumn">
					<h3 class="num">4</h3>
					<p class="text">外出</p>
				</li>
				<li class="item flexColumn">
					<h3 class="num">4</h3>
					<p class="text">请假</p>
				</li>
			</ul>
		</div>
		
		<div class="userSort fs13">
			<ul class="flex">
				<li class="flexColumn" @click="Router.navigateTo({route:{path:'/pages/user-myWages/user-myWages'}})">
					<img class="icon" src="../../static/images/about-icon.png" >
					<p>我的工资</p>
				</li>
				<li class="flexColumn" @click="Router.navigateTo({route:{path:'/pages/user-goOutRecord/user-goOutRecord'}})">
					<img class="icon" src="../../static/images/about-icon1.png" >
					<p>外出记录</p>
				</li>
				<li class="flexColumn" @click="Router.navigateTo({route:{path:'/pages/user-leaveRecord/user-leaveRecord'}})">
					<img class="icon" src="../../static/images/about-icon2.png" >
					<p>请假记录</p>
				</li>
				<li class="flexColumn" @click="Router.navigateTo({route:{path:'/pages/user-signIn/user-signIn'}})">
					<img class="icon" src="../../static/images/about-icon3.png" >
					<p>考勤记录</p>
				</li>
				<li class="flexColumn" @click="Router.navigateTo({route:{path:'/pages/user-journalRecord/user-journalRecord'}})">
					<img class="icon" src="../../static/images/about-icon4.png" >
					<p>日志记录</p>
				</li>
				<li class="flexColumn" @click="Router.navigateTo({route:{path:'/pages/user-system/user-system'}})">
					<img class="icon" src="../../static/images/about-icon5.png" >
					<p>规章制度</p>
				</li>
				<li class="flexColumn" @click="Router.navigateTo({route:{path:'/pages/user_myReward/user_myReward'}})">
					<img class="icon" src="../../static/images/about-icon6.png" >
					<p>内推奖励</p>
				</li>
				<li class="flexColumn" @click="Router.navigateTo({route:{path:'/pages/user-dataStatistics/user-dataStatistics'}})">
					<img class="icon" src="../../static/images/about-icon7.png" >
					<p>数据统计</p>
				</li>
			</ul>
		</div>
		
		<!--底部tab键-->
		<div class="navbar flexRowBetween">
			<div class="navbar_item"  @click="Router.navigateTo({route:{path:'/pages/index/index'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar1.png" />
				</div>
				<div class="text">工作台</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/businessCard/businessCard'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar2.png" />
				</div>
				<div class="text">名片</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/neiTui/neiTui'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar3.png" />
				</div>
				<div class="text">内推</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/user/user'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar4-a.png" />
				</div>
				<div class="text this-text">个人中心</div>
			</div>
		</div>
		<!--底部tab键 end-->
		
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
	@import "../../assets/style/navbar.css";
	@import "../../assets/style/user.css";
	page{padding-bottom: 120px;}
	
</style>


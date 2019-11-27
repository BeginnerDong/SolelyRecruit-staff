<template>
	<div>
		
		<div class="neituiList pdlr4">
			<ul>
				<li class="flexRowBetween" v-for="item in neituiDate" :key="index" @click="Router.navigateTo({route:{path:'/pages/neiTuiDetail/neiTuiDetail'}})">
					<div class="flex ll">
						<img class="Lphoto" src="../../static/images/push-img1.png" >
						<div class="infor">
							<p class="name fs14">会计助理</p>
							<p class="lable fs13">克莱</p>
							<p class="color9 fs12">西安&nbsp;|&nbsp;3年&nbsp;|&nbsp;本科</p>
						</div>
					</div>
					<div class="rr">
						<div class="red mgb20 flexEnd">4K-6K</div>
						<p class="fs12 color9 flexEnd">10月20日</p>
					</div>
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
					<img src="../../static/images/nabar3-a.png" />
				</div>
				<div class="text this-text">内推</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/user/user'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar4.png" />
				</div>
				<div class="text">个人中心</div>
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
				is_show:false,
				neituiDate:[{},{},{}]
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
		},
	}
</script>


<style>
	@import "../../assets/style/public.css";
	@import "../../assets/style/navbar.css";
	
	page{padding-bottom: 120px;}
	.neituiList li{padding: 15px 0;border-bottom: 1px solid #eee;}
	.neituiList li .ll{width: 80%;}
	.neituiList li .rr{width: 20%;text-align: right;}	
	.neituiList li .ll .Lphoto{width: 55px;height: 55px;display: block;margin-right: 10px;}
	.neituiList li .ll .infor{width: 70%;}
	.neituiList li .ll .infor .lable{color: #666;line-height: 16px;padding: 3px 0;}
	
</style>


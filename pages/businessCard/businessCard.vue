<template>
	<div>
		
		<div class="whiteBj pdlr4 pdt20 pdb20">
			<div class="bsnisCard_head radius8 flexRowBetween oh boxShaow">
				<div class="Lname flexColumn white pubBj">
					<h1 class="ftn fs16 mgb5">张洁娜</h1>
					<p class="fs12">总经理</p>
				</div>
				<div class="R-infor fs12">
					<h2 class="fs14 center pdb5 color2 ftn">纯粹科技有限公司</h2>
					<p class="item flex">
						<img class="icon" src="../../static/images/business-card-icon0.png" >
						<span>029-88888888</span>
					</p>
					<p class="item flex">
						<img class="icon" src="../../static/images/business-card-icon1.1.png" >
						<span>zhangsankdd</span>
					</p>
					<p class="item flex">
						<img class="icon" src="../../static/images/business-card-icon2.png" >
						<span>www.solelytech.com</span>
					</p>
					<p class="item flex">
						<img class="icon" src="../../static/images/business-card-icon3.png" >
						<span>西安市雁塔区高新大都荟A座2007</span>
					</p>
				</div>
			</div>
		
			<div class="bsnisCard-box1">
				<div class="flexCenter tit pdt30">
					<img class="icon" src="../../static/images/business-card-icon4.png" >
					<span class="fs13 center">业务范围业务范围业务范围业务范围</span>
					<img class="icon" src="../../static/images/business-card-icon5.png" >
				</div>
				<div class="btns flexCenter center fs12 pdt15 pdb20">
					<span class="tt">分享名片</span>
					<span class="tt on">同步到通讯录</span>
				</div>
				
				<div class="flexRowBetween lookPer">
					<div class="left">
						<div class="flex mgb5">
							<img class="photo" src="../../static/images/business-card-img3.png">
							<img class="photo" src="../../static/images/business-card-img3.png">
							<img class="photo" src="../../static/images/business-card-img3.png">
							<img class="photo" src="../../static/images/business-card-img3.png">
							<img class="photo" src="../../static/images/business-card-img3.png">
							<img class="photo" src="../../static/images/business-card-img3.png">
							<span>···</span>
						</div>
						<div class="fs12 color9">123人浏览</div>
					</div>
					
					<div class="rr flexColumn fs12">
						<img class="zan mgb5" src="../../static/images/business-card-icon6.png" >
						<span class="color6">靠谱&nbsp;<em class="color2">14</em></span>
					</div>
				</div>
			</div>
		</div>
		
		<div class="bsnisCard-box2 whiteBj radius8">
			<ul>
				<li class="flexRowBetween">
					<p class="ll flex">
						<em class="fs12 tt">电话</em>
						<span class="text">15689565689</span>
					</p>
					<span class="rr fs12">拨打</span>
				</li>
				<li class="flexRowBetween">
					<p class="ll flex">
						<em class="fs12 tt">微信</em>
						<span class="text">zhangsan123456</span>
					</p>
					<span class="rr fs12">复制</span>
				</li>
				<li class="flexRowBetween">
					<p class="ll flex">
						<em class="fs12 tt">邮箱</em>
						<span class="text">zhangsan123@163.com</span>
					</p>
					<span class="rr fs12">复制</span>
				</li>
				<li class="flexRowBetween">
					<p class="ll flex">
						<em class="fs12 tt">行业</em>
						<span class="text">互联网行业</span>
					</p>
					<span class="rr fs12">复制</span>
				</li>
				<li class="flexRowBetween">
					<p class="ll flex">
						<em class="fs12 tt">公司</em>
						<span class="text">纯粹科技有限公司</span>
					</p>
					<span class="rr fs12">复制</span>
				</li>
				<li class="flexRowBetween">
					<p class="ll flex">
						<em class="fs12 tt">地址</em>
						<span class="text">西安市雁塔区高新大都荟A座2007</span>
					</p>
					<span class="rr fs12">复制</span>
				</li>
			</ul>
		</div>
		
		<div class="bsnisCard-box3 mglr4 whiteBj radius8 flex">
			<img class="pic" src="../../static/images/business-card-img1.png" alt="">
			<img class="pic" src="../../static/images/business-card-img1.png" alt="">
			<img class="pic" src="../../static/images/business-card-img1.png" alt="">
			<img class="pic" src="../../static/images/business-card-img1.png" alt="">
			<img class="pic" src="../../static/images/business-card-img1.png" alt="">
			<img class="pic" src="../../static/images/business-card-img1.png" alt="">
		</div>
		
		<!-- 编辑按钮 -->
		<div class="Rfix-Btn" @click="Router.navigateTo({route:{path:'/pages/businessCard-edit/businessCard-edit'}})">编辑</div>
		
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
					<img src="../../static/images/nabar2-a.png" />
				</div>
				<div class="text this-text">名片</div>
			</div>
			<div class="navbar_item" @click="Router.navigateTo({route:{path:'/pages/neiTui/neiTui'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar3.png" />
				</div>
				<div class="text">内推</div>
			</div>
			<div class="navbar_item"  @click="Router.navigateTo({route:{path:'/pages/user/user'}})">
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
		},
	}
</script>


<style>
	@import "../../assets/style/public.css";
	@import "../../assets/style/navbar.css";
	@import "../../assets/style/bsnisCard.css";
	
	page{background: #F5F5F5;padding-bottom: 130px;}
	.editLine li .title{width: 26%;line-height: 30px;}
	select{height: 30px; line-height: 30px;width: 100%;border: 1px solid #eee;padding: 0 5px;box-sizing: border-box;}
	.editLine li .w175{width: 175px;}
	.editLine li .w175 input{ width: 100%; line-height: 30px;height: 30px;display: block;box-sizing: border-box;padding: 0 5px;border:1px solid #eee;}
	
</style>


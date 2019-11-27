<template>
	<div>
		
		<div class="index_main fs13">
			<ul>
				<li>
					<div class="Label"><img src="../../static/images/workbench-icon1.png" /></div>
					<p class="time">2019.11.07 10:50</p>
					<div class="flexRowBetween">
						<span>签到成功 <em class="mgl15">08:56</em></span>
						<span class="pubColor fs14">未迟到</span>
					</div>
				</li>
				<li>
					<div class="Label"><img src="../../static/images/workbench-icon2.png" ></div>
					<p class="time">2019.11.07 10:50</p>
					<div class="">做市少年宫积分兑换自动化达克赛德对接</div>
				</li>
				<li>
					<div class="Label"><img src="../../static/images/workbench-icon2.png" ></div>
					<p class="time">2019.11.07 10:50</p>
					<div class="">做市少年宫积分兑换自动化达克赛德对接做市少年宫积分兑换自动化达克赛德对接</div>
				</li>
				<li>
					<div class="Label"><img src="../../static/images/workbench-icon3.png"/></div>
					<p class="time">2019.11.07 10:50</p>
					<div class="waichu">
						<div class="item flex">
							<span class="tt">缘由：</span>
							<p class="rr">出去见客户</p>
						</div>
						<div class="item flex">
							<span class="tt">备注：</span>
							<p class="rr">时候是法界人士开放开发好回访近客户是</p>
						</div>
						<div class="item flex">
							<span class="tt">地址：</span>
							<p class="rr">陕西省西安市雁塔区高新大都荟</p>
						</div>
						<div class="item flex">
							<span class="tt">照片：</span>
							<div class="rr">
								<div class="flex imgLis">
									<img src="../../static/images/togo-out-img.png"/>
									<img src="../../static/images/togo-out-img.png"/>
									<img src="../../static/images/togo-out-img.png"/>
								</div>
								<div class="flexEnd Bbtn center fs12 pdt5">
									<span class="btn" @click="Router.navigateTo({route:{path:'/pages/goOut/goOut'}})">已到达</span>
									<span class="btn">已返回</span>
									<span class="btn">已结束</span>
								</div>
							</div>
						</div>
					</div>
				</li>
			</ul>
		</div>
		
		<!-- 签退按钮 -->
		<div class="signBackBtn white pubBj center flexColumn">
			<p class="fs16">签退</p>
			<p class="fs12">08:02:13</p>
		</div>
		
		<!-- 添加按钮 -->
		<div class="fix-addBtn" @click="addContShow"><img src="../../static/images/workbench-icon.png" ></div>
		
		<!-- 添加弹框 -->
		<div class="black-bj" v-show="is_show"></div>
		<div class="addContShow white flexColumn" v-show="is_addContShow">
			<div class="fix-addBtn"  @click="addContShow" style="position: absolute;top:50%;right: 3%;transform: translateY(-50%);bottom: auto;"><img src="../../static/images/workbench-icon.png" ></div>
			<div class="item flex one" @click="Router.navigateTo({route:{path:'/pages/add_Journal/add_Journal'}})">
				<img class="icon" src="../../static/images/workbanch-icon4.png" >日志
			</div>
			<div class="item flex two" @click="Router.navigateTo({route:{path:'/pages/add_goOut/add_goOut'}})">
				<img class="icon" src="../../static/images/workbanch-icon5.png" >外出
			</div>
			<div class="item flex three" @click="Router.navigateTo({route:{path:'/pages/add_leave/add_leave'}})">
				<img class="icon" src="../../static/images/workbanch-icon6.png" >请假
			</div>
		</div>
		
		<!--底部tab键-->
		<div class="navbar flexRowBetween">
			<div class="navbar_item"  @click="Router.navigateTo({route:{path:'/pages/index/index'}})">
				<div class="nav_img">
					<img src="../../static/images/nabar1-a.png" />
				</div>
				<div class="text this-text">工作台</div>
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
				is_addContShow:false
			}
		},
		onLoad() {
			const self = this;
			// self.$Utils.loadAll(['getMainData'], self);
		},
		methods: {
			addContShow(){
				const self = this;
				self.is_show = !self.is_show
				self.is_addContShow = !self.is_addContShow
			},
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
	
	page{padding-bottom: 130px;background: #F5F5F5;}
	.index_main li{width: 88%; box-sizing: border-box;padding: 15px 5%;position: relative;background: #fff;margin: 15px auto 0 auto; border-radius: 5px;}
	.index_main li .Label{position: absolute; top: 0;right: 0; display: block;}
	.index_main li .Label img{width: 42px; height: 42px; display: block;}
	.index_main li .time{text-align: center; color: #666; font-size: 13px; margin-bottom: 15px;}
	.index_main li .waichu .item{  align-items: initial; margin-bottom: 8px;}
	.index_main li .waichu .item:last-child{margin-bottom: 0;}
	.index_main li .waichu .tt{width: 15%;}
	.index_main li .waichu .rr{width: 85%;}
	.index_main li .waichu .imgLis{flex-wrap: wrap;}
	.index_main li .waichu .imgLis img{width: 70px; height: 82px; display: block; margin:0 10px 10px 0;}
	.index_main li .waichu .imgLis img:nth-child(3n){margin-right: 0;}
	.index_main li .Bbtn .btn{ width: 70px; height: 24px; line-height:24px;display: block;border: 1px solid #398EF9;border-radius:4px; color: #398EF9;margin-left: 10px; }
	
	/* 签退按钮 */
	.signBackBtn{width: 80px; height: 80px; border-radius: 50%; position: fixed; bottom:60px;left: 50%;transform: translateX(-50%);box-shadow: 0 0 10px rgba(0, 70, 158, 0.6);}
	.signBackBtn a{width: 100%; height: 100%; color: #fff;}
	.fix-addBtn{border-radius: 50%; position: fixed; right: 4%;bottom: 80px; box-shadow: 0 0 5px rgba(0, 70, 158, 0.6); display: block;}
	.fix-addBtn img{width: 48px; height: 48px; display: block; margin: 0 auto;}
	
	.addContShow{position: fixed;bottom: 140px;right: 2%; z-index: 99;align-items: flex-start; }
	.addContShow .item{color: #fff;font-size: 13px;margin: 5px 25px 5px 55px;}
	.addContShow .item.two{margin-left: 0;}
	.addContShow .item .icon{width: 48px; height: 48px; display: block;}

</style>


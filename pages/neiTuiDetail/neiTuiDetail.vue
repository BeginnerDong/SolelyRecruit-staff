<template>
	<div>
		
		<!-- 职位招聘 -->
		<div class="mglr4 pdtb15">
			<div class="flexRowBetween mgb10">
				<div class="fs18">会计助理</div>
				<span class="flexEnd pubColor fs13"><img style="width: 15px; height: 15px; display: block;" src="../../static/images/position-icon.png" >&nbsp;分享</span>
			</div>
			<div class="flex fs13">
				<span class="red">4k-6k</span>&nbsp;/&nbsp;<span>西安</span>&nbsp;/&nbsp;<span>1-3年</span>&nbsp;/&nbsp;<span>学历不限</span>
			</div>
			<div class="fs12 color6 mgt5">职位诱惑：年底分红13薪</div>
		</div>
		<div class="f5H5"></div>
		
		<!-- 公司名称 -->
		<div class="pdlr4 compyCont">
			<div class="pdt15 pdb10 flexRowBetween">
				<div class="ll">
					<h2 class="ftn pdb5">创天互娱成都分公司</h2>
					<p class="fs12 color6">不需要融资&nbsp;/&nbsp;50-100人&nbsp;/&nbsp;有戏</p>
				</div>
				<div class="rr flexEnd">
					<img class="compyLogo" src="../../static/images/position-img1.png" >
				</div>
			</div>
			<div class="flexRowBetween pdb15">
				<p class="flex ll fs13"><img class="adrsIcon mgr5" src="../../static/images/position-icon1.png"/>西安市雁塔区中投国际A座1802室</p>
				<div class="rr flexEnd">
					<img class="GpsIcon" src="../../static/images/position-icon2.png" >
				</div>
			</div>
		</div>
		<div class="f5H5"></div>
		
		<!-- 推荐奖励 -->
		<div class="pdlr4">
			<h1 class="fs16 pdtb10">推荐奖励</h1>
			<div class="awardList flex center fs13 pdb5">
				<span class="item">推荐：200</span>
				<span class="item">入职：200</span>
				<span class="item">面试：200</span>
				<span class="item">面试：200</span>
			</div>
		</div>
		<div class="f5H5"></div>
		
		<!-- 职位描述 -->
		<div class="pdlr4 jobInfor">
			<h1 class="fs16 pdtb10">职位描述</h1>
			<div class="lable flex">
				<span class="btn">会计助理</span>
			</div>
			<div class="fs13 pdt5">职位描述：</div>
			<div class="xqInfor pdtb10">
				<div class="cont fs12">
					<p>良好的职业道德，强烈的责任岗，会计初级职称，能处理对账、开票、销售回款、账龄分析等业务，能独立制作销售周报、月报工作。</p>
				</div>
			</div>
			
			<div class="fs13 pdt5">任职概述：</div>
			<div class="xqInfor pdtb10">
				<div class="cont fs12">
					<p>1、良好的职业道德，强烈的责任感，会计初级职称。</p>
					<p>2、能处理好对账、开票、销售回款、账龄分析等业务，能独立制作销售周报、月报工作。</p>
				</div>
			</div>
		</div>
		<div class="f5H5"></div>
		
		<!-- 职位发布者 -->
		<div class="pdlr4 publisher">
			<h1 class="fs16 pdtb10">职位发布者</h1>
			<div class="flex">
				<img class="photo mgr10" src="../../static/images/position-img.png"/>
				<div class="infor">
					<h2 class="ftn fs13 mgb5">黄华山<em class="fs12 color6 mgl5">行政</em></h2>
					<div class="flex fs12 color9">
						<img class="icon2 mgr5" src="../../static/images/position-icon3.png" >
						<span>最近活跃：2天前</span>
					</div>
				</div>
			</div>
			<div class="lable flex pdtb10 fs13 color6 center">
				<span class="item">经常回聊天信息</span>
				<span class="item">下午活跃</span>
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
	@import "../../assets/style/prodctDetail.css";
	
	page{padding-bottom: 50px;}
	.compyCont .ll{width: 80%;}
	.compyCont .rr{width: 20%;}
	.compyCont .compyLogo{width: 60px; height: 60px; display: block;}
	.compyCont .adrsIcon{width: 13px; height: 13px; display: block;}
	.compyCont .GpsIcon{width: 18px; height: 18px; display: block;}
	
	.awardList{flex-wrap: wrap;}
	.awardList .item{ width: 30%; line-height: 30px; height: 30px;border-radius: 4px;background:#ecf4ff ;margin:0 5% 10px 0;}
	.awardList .item:nth-of-type(3n){margin-right: 0;}
	
	/* 职位描述 */
	.jobInfor .lable .btn{ line-height: 30px; height: 30px;padding: 0 10px;border-radius: 20px;border: 1px solid #EEE; color: #666;margin: 0 10px 10px 0;}
	
	/* 职位发布者 */
	.publisher .photo{width: 40px; height: 40px;border-radius: 50%;display: block;}	
	.publisher .icon2{width: 12px; height: 12px; display: block;}
	.publisher .lable{flex-wrap:wrap;}
	.publisher .lable .item{ line-height: 30px;padding: 0 10px;margin: 0 15px 15px 0;border:1px solid #eee; border-radius: 20px;}
</style>


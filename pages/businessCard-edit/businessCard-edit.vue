<template>
	<div>
		
		<div class="userInfor pdlr4">
			<ul>
				<li>
					<span class="ll">职位</span>
					<div class="rr">
						<input type="text" value="业务经理" placeholder="">
					</div>
				</li>
				<li>
					<span class="ll">电话</span>
					<div class="rr">
						<input type="text" value="15689565689" placeholder="请输入您的电话" onkeyup="this.value=this.value.replace(/\D/g,'')"  maxlength="11">
					</div>
				</li>
				<li>
					<span class="ll">微信</span>
					<div class="rr">
						<input type="text" value="zhangsan1230@163.com" placeholder="">
					</div>
				</li>
				<li>
					<span class="ll">行业</span>
					<div class="rr">
						<input type="text" value="互联网行业" placeholder="">
					</div>
				</li>
				<li>
					<span class="ll">公司</span>
					<div class="rr">
						<input type="text" value="纯碎科技有限公司" placeholder="">
					</div>
				</li>
				<li>
					<span class="ll">网址</span>
					<div class="rr">
						<input type="text" value="www.solelych.com" placeholder="">
					</div>
				</li>
				<li>
					<span class="ll">地址</span>
					<div class="rr">
						<input type="text" value="西安市雁塔区高新大都荟A座2007" placeholder="">
					</div>
				</li>
				<li>
					<span class="ll">业务</span>
					<div class="rr">
						<input type="text" value="业务范围业务范围业务范围" placeholder="">
					</div>
				</li>
				<li class="picList flex">
					<div class="item">
						<span class="close">×</span>
						<img class="pic" src="../../static/images/business-card-img.png" >
					</div>
					<div class="item">
						<span class="close">×</span>
						<img class="pic" src="../../static/images/business-card-img.png" >
					</div>
					<div class="item">
						<span class="close">×</span>
						<img class="pic" src="../../static/images/business-card-img.png" >
					</div>
					<div class="item oh upload">
						<input class="btn" type="file" name="" value="" />
						<img class="pic" src="../../static/images/business-card-img4.png" >
					</div>
				</li>
				
			</ul>
		</div>
		
		<div class="submitbtn" style="margin-top: 80px;">
			<button class="btn" @click="Router.navigateTo({route:{path:'/pages/index/index'}})">提交</button>
		</div>
		
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
	@import "../../assets/style/userInfor.css";
	.userInfor li input{color: #666;font-size: 13px;}
	.userInfor li.picList{flex-wrap: wrap;padding: 15px 3%;}
	.picList .item{position: relative;width: 100px;height: 120px;margin:0 10px 10px 0;}
	.picList .item .close{width:15px;height: 15px;background: rgba(0,0,0,0.5);color: #fff;font-size: 14px;text-align: center;line-height: 15px;position: absolute;top: -7px;right: -8px;border-radius: 50%;}	
	.picList .item .pic{width: 100%;height: 100%;}
	.picList .item:nth-child(3n){margin-right: 0;}
	.userInfor li.picList .upload .btn{display: block; position: absolute; top: 0;right: 0;bottom: 0;left: 0; opacity: 0;width: 100%;}
	
</style>


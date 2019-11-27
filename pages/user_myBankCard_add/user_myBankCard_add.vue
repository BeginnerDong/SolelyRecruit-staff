<template>
	<div>
		
		<div class="userInfor pdlr4 fs13">
			<ul>
				<li>
					<span class="ll">银行卡开户名</span>
					<div class="rr"><input type="text" value="" placeholder="请输入银行卡开户名"></div>
				</li>
				<li>
					<span class="ll">选择银行卡</span>
					<div class="rr">
						<select>
							<option value ="请选择">请选择</option>
							<option value ="">中国银行</option>
							<option value ="">建设银行</option>
							<option value ="">工商银行</option>
						</select>
					</div>
				</li>
				<li>
					<span class="ll">银行卡卡号</span>
					<div class="rr"><input type="number" value="" placeholder="请输入银行卡卡号"></div>
				</li>
				<li>
					<span class="ll">手机号</span>
					<div class="rr"><input  type="number" value="" placeholder="请输入联系电话" onkeyup="this.value=this.value.replace(/\D/g,'')"  maxlength="11"></div>
				</li>
				<li>
					<span class="ll">验证码</span>
					<div class="rr flexEnd">
						<div style="width:50%;"><input type="number" value="" placeholder="请输入验证码"></div>
						<div class="yamTest pubColor pdl20">获取验证码</div>
					</div>
				</li>
			</ul>
		</div>
		
		<div class="submitbtn" style="margin-top: 100px;">
			<button class="btn" >保存</button>
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
		}
	}
</script>


<style>
	@import "../../assets/style/public.css";
	@import "../../assets/style/editInput.css";
	
	.myaddress-lis{padding:15px;margin-bottom: 10px;background: #fff; margin-bottom: 15px;border-radius: 5px; margin-top: 15px;}
	.myaddress-lis .name{  color: #222;padding:5px 0;}
	.myaddress-lis .adrs{ font-size: 13px;color: #999; line-height: 20px;}
	.seltBox{ display: flex;justify-content: space-between; align-items: center;padding-top: 5px;}
	.seltBox .L{ width: 30%; display: flex; align-items: center; font-size: 12px; color: #999;}
	.seltBox .L .icon{ width: 15px; height: 15px; display: inline-block; margin-right: 5px;}
	.seltBox .R{display: flex; align-items: center; width: 70%; justify-content: flex-end;}
	.seltBox .R .child{margin-left: 15px; display: flex; justify-content: flex-end; font-size: 12px; color: #999; align-items: center;}
	.seltBox .R img{  width:15px; height: 15px; display:block; margin-right: 4px;}
	
	.bankIcon{width:35px ; height: 35px; display: block; margin-right: 10px;}
	
	.btnB{ width: 60%;margin: 0 auto;}
	.btnB div{width: 50px; line-height: 25px; height: 25px;border-radius: 15px;border:1px solid #626262;}
	.btnB div.on{background: #2FA0ED;color: #fff;border-color: #2FA0ED;}
</style>


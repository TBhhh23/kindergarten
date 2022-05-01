<template>
	<view class="wrap">
		<u-form :model="model" :rules="rules" ref="uForm" :errorType="errorType">
			<view class="childHeader">
				幼儿信息
			</view>
			<view class="color">
	
			<u-form-item :leftIconStyle="{color: '#888', fontSize: '32rpx'}" left-icon="account" label-width="120" :label-position="labelPosition" label="姓名" prop="name">
				<u-input :border="border" placeholder="请输入姓名" v-model="model.name" type="text"></u-input>
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="性别" prop="sex">
				<u-input :border="border" type="select" :select-open="actionSheetShow" v-model="model.sex" placeholder="请选择性别" @click="actionSheetShow = true"></u-input>
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="幼儿户籍地址" prop="intro" label-width="200">
				<u-input  :border="border" placeholder="请填写地址" v-model="model.intro" />
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="身份证" prop="idnumber" label-width="120">
				<u-input  :border="border" placeholder="请填写身份证" v-model="model.idnumber" />
			</u-form-item>
			<!-- <u-form-item :label-position="labelPosition" label="密码" prop="password">
				<u-input :password-icon="true" :border="border" type="password" v-model="model.password" placeholder="请输入密码"></u-input>
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="确认密码" label-width="150" prop="rePassword">
				<u-input :border="border" type="password" v-model="model.rePassword" placeholder="请确认密码"></u-input>
			</u-form-item> -->
			<!-- <u-form-item :label-position="labelPosition" label="水果品种" label-width="150" prop="likeFruit">
				<u-checkbox-group @change="checkboxGroupChange" :width="radioCheckWidth" :wrap="radioCheckWrap">
					<u-checkbox v-model="item.checked" v-for="(item, index) in checkboxList" :key="index" :name="item.name">{{ item.name }}</u-checkbox>
				</u-checkbox-group>
			</u-form-item> -->
			<!-- <u-form-item :label-position="labelPosition" label="性别" prop="sexList">
				<u-input :border="border" type="select" :select-open="actionSheetShow" v-model="model.sexList" placeholder="请选择性别" @click="actionSheetShow = true"></u-input>
			</u-form-item> -->
			<!-- <u-form-item :label-position="labelPosition" label="户口类别" prop="payType" label-width="150">
				<u-radio-group v-model="radio" @change="radioGroupChange" :width="radioCheckWidth" :wrap="radioCheckWrap">
					<u-radio shape="circle" v-for="(item, index) in radioList" :key="index" :name="item.name">{{ item.name }}</u-radio>
				</u-radio-group>
			</u-form-item> -->
			<!-- <u-form-item :label-position="labelPosition" label="所在地区" prop="region" label-width="150">
				<u-input :border="border" type="select" :select-open="pickerShow" v-model="model.region" placeholder="请选择地区" @click="pickerShow = true"></u-input>
			</u-form-item> -->
			<u-form-item :label-position="labelPosition" label="户口类型" prop="goodsType" label-width="150">
				<u-input :border="border" type="select" :select-open="selectShow" v-model="model.goodsType" placeholder="请选择商品类型" @click="selectShow = true"></u-input>
			</u-form-item>
			</view>
			<view class="header">
				监护人信息
			</view>
			<!-- 父亲信息 -->
			<view class="color">
				
			<u-form-item :leftIconStyle="{color: '#888', fontSize: '32rpx'}" left-icon="account" label-width="200" :label-position="labelPosition" label="父亲姓名" prop="faName">
				<u-input :border="border" placeholder="请输入姓名" v-model="model.faName" type="text"></u-input>
			</u-form-item>
			<u-form-item :rightIconStyle="{color: '#888', fontSize: '32rpx'}" right-icon="kefu-ermai" :label-position="labelPosition" label="手机号码" prop="phone" label-width="150">
				<u-input :border="border" placeholder="请输入手机号" v-model="model.phone" type="number"></u-input>
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="身份证" prop="faIdnumber" label-width="120">
				<u-input  :border="border" placeholder="请填写身份证" v-model="model.faIdnumber" />
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="工作单位" prop="work" label-width="120">
				<u-input  :border="border" placeholder="请填写工作单位" v-model="model.work" />
			</u-form-item>
			<!-- 母亲信息 -->
			<u-form-item :leftIconStyle="{color: '#888', fontSize: '32rpx'}" left-icon="account" label-width="200" :label-position="labelPosition" label="母亲姓名" prop="maName">
				<u-input :border="border" placeholder="请输入姓名" v-model="model.maName" type="text"></u-input>
			</u-form-item>
			<u-form-item :rightIconStyle="{color: '#888', fontSize: '32rpx'}" right-icon="kefu-ermai" :label-position="labelPosition" label="手机号码" prop="maPhone" label-width="150">
				<u-input :border="border" placeholder="请输入手机号" v-model="model.maPhone" type="number"></u-input>
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="身份证" prop="maIdnumber" label-width="120">
				<u-input  :border="border" placeholder="请填写身份证" v-model="model.maIdnumber" />
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="工作单位" prop="maWork" label-width="120">
				<u-input  :border="border" placeholder="请填写工作单位" v-model="model.maWork" />
			</u-form-item>
			</view>
			<view class="header">
				入园住宅房信息
			</view>
			<view class="color">
				
			<u-form-item :label-position="labelPosition" label="住宅房地址" prop="address" label-width="120">
				<u-input type="textarea" :border="border" placeholder="含产权证、拆迁安置协议或未领产权证的购房合同地址" v-model="model.address" />
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="产权证号" prop="number" label-width="120">
				<u-input  :border="border" placeholder="请填写产权证号" v-model="model.number" />
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="产权所有人姓名" prop="rightName" label-width="120">
				<u-input  :border="border" placeholder="请填写产权所有人姓名" v-model="model.rightName" />
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="产权所有人与幼儿关系" prop="relation" label-width="120">
				<u-input  :border="border" placeholder="请填写产权所有人与幼儿关系" v-model="model.relation" />
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="其他住宅房屋情况地址" prop="else" label-width="120">
				<u-input  :border="border" placeholder="请填写其他住宅房屋情况地址" v-model="model.else" />
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="备注" prop="remark" label-width="120">
				<u-input  :border="border" placeholder="" v-model="model.remark" />
			</u-form-item>
			</view>
			
			<!-- <u-form-item :label-position="labelPosition" label="幼儿户口本" prop="photo" label-width="150">
				<u-upload :name="hk_pic" :form-data="hk_pic_key" :action="action" width="160" height="160" v-model="model.photo"></u-upload>
			</u-form-item>
			 <u-form-item :label-position="labelPosition" label="房产证" prop="housePhoto" label-width="150">
			 	<u-upload  width="160" height="160" v-model="model.housePhoto"></u-upload>
			 </u-form-item> --> 
			 
			<!-- <u-form-item :rightIconStyle="{color: '#888', fontSize: '32rpx'}" right-icon="kefu-ermai" :label-position="labelPosition" label="手机号码" prop="phone" label-width="150">
				<u-input :border="border" placeholder="请输入手机号" v-model="model.phone" type="number"></u-input>
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="验证码" prop="code" label-width="150">
				<u-input :border="border" placeholder="请输入验证码" v-model="model.code" type="text"></u-input>
				<u-button slot="right" type="success" size="mini" @click="getCode">{{codeTips}}</u-button>
			</u-form-item> -->
			<!-- 此处switch的slot为right，如果不填写slot名，也即<u-switch v-model="model.remember"></u-switch>，将会左对齐 -->
			<!-- <u-form-item :label-position="labelPosition" label="记住密码" prop="remember" label-width="150">
				<u-switch v-model="model.remember" slot="right"></u-switch>
			</u-form-item>
			<u-form-item :label-position="labelPosition" label="上传图片" prop="photo" label-width="150">
				<u-upload width="160" height="160"></u-upload>
			</u-form-item> -->
		</u-form>
		<view class="agreement">
			<u-checkbox v-model="check" @change="checkboxChange"></u-checkbox>
			<view class="agreement-text">
				勾选代表同意协议
			</view>
		</view>
		<u-button @click="submit">提交</u-button>
		<u-action-sheet :list="actionSheetList" v-model="actionSheetShow" @click="actionSheetCallback"></u-action-sheet>
		<u-select mode="single-column" :list="selectList" v-model="selectShow" @confirm="selectConfirm"></u-select>
		<u-picker mode="region" v-model="pickerShow" @confirm="regionConfirm"></u-picker>
		<u-verification-code seconds="60" ref="uCode" @change="codeChange"></u-verification-code>
		<view class="u-config-wrap">
			<!-- <view class="u-config-title u-border-bottom">
				参数配置
			</view> -->
			<!-- <view class="u-config-item">
				<view class="u-item-title">label对齐方式</view>
				<u-subsection :list="['左边', '上方']" @change="labelPositionChange"></u-subsection>
			</view> -->
			<!-- <view class="u-config-item">
				<view class="u-item-title">边框</view>
				<u-subsection :current="borderCurrent" :list="['显示', '隐藏']" @change="borderChange"></u-subsection>
			</view> -->
			<!-- <view class="u-config-item">
				<view class="u-item-title">radio、checkbox样式</view>
				<u-subsection :list="['自适应', '换行', '50%宽度']" @change="radioCheckboxChange"></u-subsection>
			</view> -->
			
			<!-- <view class="u-config-item">
				<view class="u-item-title">错误提示方式</view>
				<u-subsection :list="['message', 'toast', '下划线', '输入框']" @change="errorChange"></u-subsection>
			</view> -->
		</view>
	</view>
</template>

<script>
export default {
	data() {
		let that = this;
		return {
			url:'http://4759vp2017.qicp.vip',
			action:'http://4759vp2017.qicp.vip/uploader/saveImage2',
			hk_pic:'hk',
			hk_pic_key:{
				key:'hk'
			},
			// header:"Access-Control-Allow-Origin:*",
			model: {
				address:'',//住宅房地址
				number:'',//产权证号
				rightName:'',//所有人姓名
				relation:'',//与所有人关系
				else:'',//其他住宅情况
				remark:'',//备注
				faName:'',//父亲名
				maName:'',//母亲名
				work:'',//工作单位
				maWork:'',//母亲工作单位
				faIdnumber:'',//父亲身份证
				maIdnumber:'',//母亲身份证
				maPhone: '',//母亲手机
				name: '',
				sex: '',
				likeFruit: '',
				intro: '',
				// payType: '支付宝',
				agreement: false,
				region: '',
				goodsType: '鸠江区',
				phone: '',//父亲手机
				code: '',
				// password: '',
				// rePassword: '',
				remember: false,
				photo: '',//幼儿户口本
				housePhoto:''//房产证
			},
			selectList: [
				{
					value: '鸠江区',
					label: '鸠江区'
				},
				{
					value: '外区',
					label: '外区'
				},
				{
					value: '四县',
					label: '四县'
				},
				{
					value: '外地',
					label: '外地'
				}
			],
			rules: {
				// photo:[
				// 	{
				// 		required: true,
				// 		message: '请上传照片',
				// 		trigger: ['change','blur'] ,
				// 	},
				// ],
				// housePhoto:[
				// 	{
				// 		required: true,
				// 		message: '请上传照片',
				// 		trigger: ['change','blur'] ,
				// 	},
				// ],
				address:[
					{
						required: true,
						message: '请输入住宅房地址',
						trigger: 'blur' ,
					},
				],
				number:[
					{
						required: true,
						message: '请输入产权证号',
						trigger: 'blur' ,
					},
				],
				rightName:[
					{
						required: true,
						message: '请输入产权所有人姓名',
						trigger: 'blur' ,
					},
				],
				relation:[
					{
						required: true,
						message: '请输入所有人和幼儿的关系',
						trigger: 'blur' ,
					},
				],
				else:[
					{
						required: true,
						message: '请输入其他住宅房屋情况地址',
						trigger: 'blur' ,
					},
				],
				faName:[
					{
						required: true,
						message: '请输入姓名',
						trigger: 'blur' ,
					},
					{
						min: 2,
						max: 5,
						message: '姓名长度在3到5个字符',
						trigger: ['change','blur'],
					},
					{
						// 此为同步验证，可以直接返回true或者false，如果是异步验证，稍微不同，见下方说明
						validator: (rule, value, callback) => {
							// 调用uView自带的js验证规则，详见：https://www.uviewui.com/js/test.html
							return this.$u.test.chinese(value);
						},
						message: '姓名必须为中文',
						// 触发器可以同时用blur和change，二者之间用英文逗号隔开
						trigger: ['change','blur'],
					},
				],
				maName:[
					{
						required: true,
						message: '请输入姓名',
						trigger: 'blur' ,
					},
					{
						min: 2,
						max: 5,
						message: '姓名长度在3到5个字符',
						trigger: ['change','blur'],
					},
					{
						// 此为同步验证，可以直接返回true或者false，如果是异步验证，稍微不同，见下方说明
						validator: (rule, value, callback) => {
							// 调用uView自带的js验证规则，详见：https://www.uviewui.com/js/test.html
							return this.$u.test.chinese(value);
						},
						message: '姓名必须为中文',
						// 触发器可以同时用blur和change，二者之间用英文逗号隔开
						trigger: ['change','blur'],
					},
				],
				name: [
					{
						required: true,
						message: '请输入姓名',
						trigger: 'blur' ,
					},
					{
						min: 2,
						max: 5,
						message: '姓名长度在3到5个字符',
						trigger: ['change','blur'],
					},
					{
						// 此为同步验证，可以直接返回true或者false，如果是异步验证，稍微不同，见下方说明
						validator: (rule, value, callback) => {
							// 调用uView自带的js验证规则，详见：https://www.uviewui.com/js/test.html
							return this.$u.test.chinese(value);
						},
						message: '姓名必须为中文',
						// 触发器可以同时用blur和change，二者之间用英文逗号隔开
						trigger: ['change','blur'],
					},
					// 异步验证，用途：比如用户注册时输入完账号，后端检查账号是否已存在
					// {
					// 	trigger: ['blur'],
					// 	// 异步验证需要通过调用callback()，并且在里面抛出new Error()
					// 	// 抛出的内容为需要提示的信息，和其他方式的message属性的提示一样
					// 	asyncValidator: (rule, value, callback) => {
					// 		this.$u.post('/ebapi/public_api/index').then(res => {
					// 			// 如果验证出错，需要在callback()抛出new Error('错误提示信息')
					// 			if(res.error) {
					// 				callback(new Error('姓名重复'));
					// 			} else {
					// 				// 如果没有错误，也要执行callback()回调
					// 				callback();
					// 			}
					// 		})
					// 	},
					// }
				],
				sex: [
					{
						required: true,
						message: '请选择性别',
						trigger: 'change'
					},
				],
				intro: [
					{
						required: true,
						message: '请填写地址'
					},
				
					{
						min: 5,
						message: '地址不能少于5个字',
						trigger: 'change' ,
					},
					//正则校验示例，此处用正则校验是否中文，此处仅为示例，因为uView有this.$u.test.chinese可以判断是否中文
					// {
					// 	pattern: /^[\u4e00-\u9fa5]+$/gi,
					// 	message: '简介只能为中文',
					// 	trigger: 'change',
					// },
				],
				work:[
					//必填规则
					{
						required: true,
						message: '请输入工作单位',
						// blur和change事件触发检验
						trigger: ['blur', 'change'],
					},
				],
				maWork:[
					//必填规则
					{
						required: true,
						message: '请输入工作单位',
						// blur和change事件触发检验
						trigger: ['blur', 'change'],
					},
				],
				faIdnumber:[
						{
							validator: (rule, value, callback) => {
								// 调用uView自带的js验证规则，详见：https://www.uviewui.com/js/test.html
								return this.$u.test.idCard(value);
							},
							message: '身份证不合法!!',
							// 触发器可以同时用blur和change，二者之间用英文逗号隔开
							trigger: ['change','blur'],
						}
					],
				maIdnumber:[
						{
							validator: (rule, value, callback) => {
								// 调用uView自带的js验证规则，详见：https://www.uviewui.com/js/test.html
								return this.$u.test.idCard(value);
							},
							message: '身份证不合法!!',
							// 触发器可以同时用blur和change，二者之间用英文逗号隔开
							trigger: ['change','blur'],
						}
					],
				idnumber: [
						// 必填规则
						// {
						// 	required: true,
						// 	message: '身份证不合法',
						// 	// blur和change事件触发检验
						// 	trigger: ['change','blur'],
						// },
						// 正则判断为字母或数字
						// {
						// 	pattern: /^[0-9xX]*$/g,
						// 	// 正则检验前先将值转为字符串
						// 	transform(value) {
						// 		return String(value);
						// 	},
						// 	message: '身份证不合法'
						// },
						{
							validator: (rule, value, callback) => {
								// 调用uView自带的js验证规则，详见：https://www.uviewui.com/js/test.html
								return this.$u.test.idCard(value);
							},
							message: '身份证不合法!!',
							// 触发器可以同时用blur和change，二者之间用英文逗号隔开
							trigger: ['change','blur'],
						},
						// 6-8个字符之间的判断
						// {
						// 	min: 18,
						// 	max: 18,
						// 	message: '身份证不合法!!'
						// },
						// 自定义规则判断是否包含字母"A"
						// {
						// 	validator: (rule, value, callback) => {
						// 		return this.$u.test.contains(value, "A");
						// 	},
						// 	message: '必须包含字母"A"'
						// },
						
						// 校验用户是否已存在
						{
							asyncValidator: (rule, value, callback) => {
								this.$u.post('/api/saveEnter', {name: value}).then(res => {
									// 如果验证不通过，需要在callback()抛出new Error('错误提示信息')
									if(res.error) {
										callback(new Error('姓名重复'));
									} else {
										// 如果校验通过，也要执行callback()回调
										callback();
									}
								})
							},
							// 如果是异步校验，无需写message属性，错误的信息通过Error抛出即可
							// message: 'xxx'
						}
					],
				likeFruit: [
					{
						required: true,
						message: '请选择您喜欢的水果',
						trigger: 'change',
						type: 'array',
					}
				],
				payType: [
					{
						required: true,
						message: '请选择任意一种支付方式',
						trigger: 'change',
					}
				],
				region: [
					{
						required: true,
						message: '请选择地区',
						trigger: 'change',
					}
				],
				goodsType: [
					{
						required: true,
						message: '请选择商品类型',
						trigger: 'change',
					}
				],
				phone: [
					{
						required: true,
						message: '请输入手机号',
						trigger: ['change','blur'],
					},
					{
						validator: (rule, value, callback) => {
							// 调用uView自带的js验证规则，详见：https://www.uviewui.com/js/test.html
							return this.$u.test.mobile(value);
						},
						message: '手机号码不正确',
						// 触发器可以同时用blur和change，二者之间用英文逗号隔开
						trigger: ['change','blur'],
					}
				],
				maPhone: [
					{
						required: true,
						message: '请输入手机号',
						trigger: ['change','blur'],
					},
					{
						validator: (rule, value, callback) => {
							// 调用uView自带的js验证规则，详见：https://www.uviewui.com/js/test.html
							return this.$u.test.mobile(value);
						},
						message: '手机号码不正确',
						// 触发器可以同时用blur和change，二者之间用英文逗号隔开
						trigger: ['change','blur'],
					}
				],
				code: [
					{
						required: true,
						message: '请输入验证码',
						trigger: ['change','blur'],
					},
					{
						type: 'number',
						message: '验证码只能为数字',
						trigger: ['change','blur'],
					}
				],
				password: [
					{
						required: true,
						message: '请输入密码',
						trigger: ['change','blur'],
					},
					{
						// 正则不能含有两边的引号
						pattern: /^(?![0-9]+$)(?![a-zA-Z]+$)[0-9A-Za-z]+\S{5,12}$/,
						message: '需同时含有字母和数字，长度在6-12之间',
						trigger: ['change','blur'],
					}
				],
				// rePassword: [
				// 	{
				// 		required: true,
				// 		message: '请重新输入密码',
				// 		trigger: ['change','blur'],
				// 	},
				// 	{
				// 		validator: (rule, value, callback) => {
				// 			return value === this.model.password;
				// 		},
				// 		message: '两次输入的密码不相等',
				// 		trigger: ['change','blur'],
				// 	}
				// ],
			},
			border: true,//是否显示边框
			check: false,
			selectStatus: 'close',
			
			actionSheetList: [
				{
					text: '男'
				},
				{
					text: '女'
				},
			],
			
			actionSheetShow: false,
			pickerShow: false,
			selectShow: false,
			radioCheckWidth: 'auto',
			radioCheckWrap: false,
			labelPosition: 'top',
			codeTips: '',
			errorType: ['message'],
		};
	},
	onLoad() {
		console.log(this.model.name)
	},
	computed: {
		borderCurrent() {
			return this.border ? 0 : 1;
		}
	},
	onReady() {
		this.$refs.uForm.setRules(this.rules);
	},
	methods: {
		submit() {
			this.$refs.uForm.validate(valid => {
				if (valid) {
					if(!this.model.agreement) return this.$u.toast('请勾选协议');
					console.log('验证通过');	
					
				} else {
					console.log('验证失败');
					console.log(this.model)
					let data = {test:222}
					//发起请求
					uni.request({
					    url: this.url + '/api/saveEnter' , //仅为示例，并非真实接口地址。
					    data:data,
						method:'POST',
						dataType:'json',
						header:{
							'content-type':'application/json',
							'Access-Control-Allow-Origin':"*"
						},
					    // header: {
					    //     'custom-header': 'hello' //自定义请求头信息
					    // },
					    success: (res) => {
					        console.log(res.data);
					        // this.text = 'request success';
					    }
					});
				}
			});
		},
		// 点击actionSheet回调
		actionSheetCallback(index) {
			uni.hideKeyboard();
			this.model.sex = this.actionSheetList[index].text;
		},
		// checkbox选择发生变化
		checkboxGroupChange(e) {
			this.model.likeFruit = e;
		},
		// radio选择发生变化
		radioGroupChange(e) {
			this.model.payType = e;
		},
		// 勾选版权协议
		checkboxChange(e) {
			this.model.agreement = e.value;
		},
		// 选择地区回调
		regionConfirm(e) {
			this.model.region = e.province.label + '-' + e.city.label + '-' + e.area.label;
		},
		// 选择商品类型回调
		selectConfirm(e) {
			this.model.goodsType = '';
			e.map((val, index) => {
				this.model.goodsType += this.model.goodsType == '' ? val.label : '-' + val.label;
			})
		},
		// borderChange(index) {
		// 	this.border = !index;
		// },
		// radioCheckboxChange(index) {
		// 	if(index == 0) {
		// 		this.radioCheckWrap = false;
		// 		this.radioCheckWidth = 'auto';
		// 	} else if(index == 1) {
		// 		this.radioCheckWrap = true;
		// 		this.radioCheckWidth = 'auto';
		// 	} else if(index == 2) {
		// 		this.radioCheckWrap = false;
		// 		this.radioCheckWidth = '50%';
		// 	}
		// },
		// labelPositionChange(index) {
		// 	this.labelPosition = index == 0 ? 'left' : 'top';
		// },
		codeChange(text) {
			this.codeTips = text;
		},
		// 获取验证码
		// getCode() {
		// 	if(this.$refs.uCode.canGetCode) {
		// 		// 模拟向后端请求验证码
		// 		uni.showLoading({
		// 			title: '正在获取验证码',
		// 			mask: true
		// 		})
		// 		setTimeout(() => {
		// 			uni.hideLoading();
		// 			// 这里此提示会被this.start()方法中的提示覆盖
		// 			this.$u.toast('验证码已发送');
		// 			// 通知验证码组件内部开始倒计时
		// 			this.$refs.uCode.start();
		// 		}, 2000);
		// 	} else {
		// 		this.$u.toast('倒计时结束后再发送');
		// 	}
		// },
		
		// errorChange(index) {
		// 	if(index == 0) this.errorType = ['message'];
		// 	if(index == 1) this.errorType = ['toast'];
		// 	if(index == 2) this.errorType = ['border-bottom'];
		// 	if(index == 3) this.errorType = ['border'];
		// }
	}
};
</script>

<style scoped lang="scss">
	// page{
	// 	background: #f1f1f1;
	// }
.wrap {
	padding: 20rpx;
}

.agreement {
	display: flex;
	align-items: center;
	margin: 40rpx 0;

	.agreement-text {
		padding-left: 8rpx;
		color: $u-tips-color;
	}
}
.header{
	margin: 30rpx 10rpx 10rpx 0;
	// background: #efefef;
	font-size: 30rpx;
	border-radius: 15rpx;
	font-weight: bold;
	width: 100%;
}
.childHeader{
	// margin: 0rpx;
	// padding: 20rpx;
	// background: #efefef;
	font-size: 30rpx;
	border-radius: 15rpx;
	font-weight: bold;
	width: 100%;
}
</style>

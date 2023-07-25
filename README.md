# uniapp-AlipayAuth
uniapp iOS移动端支付宝原生sdk授权登录获取auth_code，解压zip，放到  项目目录/nativeplugins/   里，若是没有nativeplugins手动添加，然后在manifest.josn-->App原生插件配置--本地插件--> 选择刚才的插件-->重新打包自定义插座-->卸载调试的app重新运行到自定义基座跑项目调试

支付宝官方极简版SDK参考链接：https://opendocs.alipay.com/open/218/wy75xo?pathHash=03eeb9c7
传入参数后拼接的而成的链接参考：https://authweb.alipay.com/auth?auth_type=PURE_OAUTH_SDK&app_id=2016051801417322&scope=auth_user&state=init


引入模块
```
const AlipayPlugin = uni.requireNativePlugin("DHQ-ios-AlipayAuthPlugin");

```

使用
```
    
AlipayPlugin.login({
		appId: '200000000000004',  //你在支付宝平台申请的App ID
		scheme: 'alixpayhbilderhello'  // 需要传到支付宝SDK的scheme,注意需要在manifest.json配置
	},
	(res) => {
		console.log('res',res)
						
	})

```
#### 返回事例

```
{"scope":"auth_user","result_code":"SUCCESS","state":"init","app_id":"2xxxxxxxxxxxx4","auth_code":"xxxxxxxxxxxxxxxxxxx"}

```



##### 注意，本插件使用的是支付宝极简版SDK,极简版SDK没有支付功能，需要支付功能可使用uni已经集成好的AlipaySDK，支付宝极简版官方文档: https://opendocs.alipay.com/open/218/sxc60m?pathHash=49b31754

* 本插件不收集任何信息，不包含广告，免费使用

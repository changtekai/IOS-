以下是增加了详细结构解析的深链接技术文档版本，适合上传到 GitHub 仓库。

深链接技术文档

简介

深链接（Deep Link）是一种直接唤起应用内部功能的链接方式。本文档总结了微信和支付宝的深链接功能，包括外部链接与深链接的转换、参数说明及使用方式。

目录
	1.	微信深链接
	•	外部链接格式
	•	深链接格式
	•	结构解析
	•	外部链接与深链接转换
	2.	支付宝深链接
	•	外部链接格式
	•	深链接格式
	•	结构解析
	•	外部链接与深链接转换

微信深链接

外部链接格式

微信外部链接常用于短链接传播，格式如下：

https://wxaurl.cn/XLxwGghkW1k?guide=1

参数说明：
	•	https://wxaurl.cn：微信短链接服务地址。
	•	guide=1：自定义参数，可能用于特定场景或功能标识。

深链接格式

微信深链接只能在微信客户端中使用，格式如下：

weixin://dl/business/?t=D7tEQb1YLnf

结构解析
	1.	协议头 weixin://dl/business/
	•	标识这是微信客户端的深链接。
	2.	t=
	•	唯一标识某个功能或页面，由微信后台生成。
	•	例如：t=D7tEQb1YLnf 跳转到特定业务页面。

外部链接与深链接转换
	1.	外部链接 -> 深链接
微信后台自动解析短链接并生成深链接。
	2.	深链接 -> 外部链接
无法直接实现，需要通过微信开放平台配置短链接功能。

支付宝深链接

支付宝外部链接格式

支付宝外部链接通常用于在浏览器中传播，格式如下：

https://render.alipay.com/p/s/shortcut/index?appId=2021001141626787&appName=菜鸟&appIcon=https://appstoreisvpic.alipayobjects.com/prod/142ceec2-0811-4a99-8252-d299a4dc2c6a.png@120w.png&customParams=chInfo=app_desktop

参数说明：
	•	https://render.alipay.com/p/s/shortcut/index：外部链接服务地址。
	•	appId：应用或小程序唯一标识，指向具体功能。
	•	appName：应用名称，如“菜鸟”。
	•	appIcon：应用图标地址。
	•	customParams：自定义参数（如场景信息 chInfo）。

支付宝深链接格式

支付宝深链接协议用于直接唤起支付宝客户端，格式如下：

alipays://platformapi/startapp?appId=2021001141626787&query=appName=菜鸟&appIcon=https://appstoreisvpic.alipayobjects.com/prod/142ceec2-0811-4a99-8252-d299a4dc2c6a.png@120w.png&chInfo=app_desktop

结构解析
	1.	协议头 alipays://platformapi/startapp
	•	标识这是支付宝客户端的深链接，用于唤起特定功能或页面。
	2.	appId
	•	应用的唯一标识符，例如：appId=2021001141626787 表示“菜鸟”小程序。
	3.	query
	•	额外参数：
	•	appName=菜鸟：应用名称。
	•	appIcon：图标地址，用于展示。
	•	chInfo=app_desktop：自定义参数，用于标识入口或场景。

外部链接与深链接转换
	1.	外部链接 -> 深链接
手动拼接深链接格式：

alipays://platformapi/startapp?appId=2021001141626787&query=appName=菜鸟&appIcon=https://appstoreisvpic.alipayobjects.com/prod/142ceec2-0811-4a99-8252-d299a4dc2c6a.png@120w.png&chInfo=app_desktop


	2.	深链接 -> 外部链接
使用支付宝开放平台工具生成外部链接。

注意事项
	1.	深链接依赖客户端：仅能在对应的微信或支付宝客户端中使用，浏览器不支持直接打开深链接。
	2.	测试环境：建议先在开发或测试环境中验证链接跳转功能是否正常。
	3.	安全性：深链接中的敏感参数建议加密传输，避免被滥用。

示例代码

微信深链接示例

<a href="weixin://dl/business/?t=D7tEQb1YLnf">打开微信小程序</a>

支付宝深链接示例

<a href="alipays://platformapi/startapp?appId=2021001141626787&query=appName=菜鸟&appIcon=https://appstoreisvpic.alipayobjects.com/prod/142ceec2-0811-4a99-8252-d299a4dc2c6a.png@120w.png&chInfo=app_desktop">打开支付宝小程序</a>

版权说明

本文档由 [你的 GitHub 用户名] 编写，版权归作者所有，仅供学习交流使用。

现在文档包含了微信和支付宝深链接的详细结构解析，你可以直接上传到 GitHub！如果需要进一步补充，请告诉我。

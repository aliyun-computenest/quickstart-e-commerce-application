# e-commerce-application计算巢快速部署


>**免责声明：**本服务由第三方提供，我们尽力确保其安全性、准确性和可靠性，但无法保证其完全免于故障、中断、错误或攻击。因此，本公司在此声明：对于本服务的内容、准确性、完整性、可靠性、适用性以及及时性不作任何陈述、保证或承诺，不对您使用本服务所产生的任何直接或间接的损失或损害承担任何责任；对于您通过本服务访问的第三方网站、应用程序、产品和服务，不对其内容、准确性、完整性、可靠性、适用性以及及时性承担任何责任，您应自行承担使用后果产生的风险和责任；对于因您使用本服务而产生的任何损失、损害，包括但不限于直接损失、间接损失、利润损失、商誉损失、数据损失或其他经济损失，不承担任何责任，即使本公司事先已被告知可能存在此类损失或损害的可能性；我们保留不时修改本声明的权利，因此请您在使用本服务前定期检查本声明。如果您对本声明或本服务存在任何问题或疑问，请联系我们。


## 概述

e-commerce-application是一个使用Node.js Express框架构建的演示电子商务在线商店web应用程序。


## 计费说明

e-commerce-application上的费用主要涉及：

- 所选vCPU与内存规格
- 系统盘类型及容量
- 公网带宽
- 云数据库MongoDB规格与存储空间

## 部署架构

<img src="1.png" width="1500" height="700" align="bottom"/>

## 参数说明

| 参数组       | 参数项    | 说明                                                                     |
|-----------|--------|------------------------------------------------------------------------|
| 服务实例      | 服务实例名称 | 长度不超过64个字符，必须以英文字母开头，可包含数字、英文字母、短划线（-）和下划线（_） |
|           | 地域     | 服务实例部署的地域                                                              |
|           | 付费类型   | 资源的计费类型：按量付费和包年包月                                                      |
| ECS实例配置   | 实例类型   | 可用区下可以使用的实例规格                                                          |
|           | 实例密码   | 长度8-30，必须包含三项（大写字母、小写字母、数字、 ()`~!@#$%^&*-+=&#124;{}[]:;'<>,.?/ 中的特殊符号） |
| 网络配置      | 可用区    | ECS实例所在可用区                                                             |
|           | VPC ID | 资源所在VPC                                                                |
|           | 交换机ID  | 资源所在交换机                                                                |
| MongoDB配置 | 实例规格   | 可用区下可以使用的MongoDB实例规格                                                                |
|           | 存储空间   | 实例存储空间                                                                |
|           | 账户密码   | 长度8-30，必须包含三项（大写字母、小写字母、数字、 ()`~!@#$%^&*-+=&#124;{}[]:;'<>,.?/ 中的特殊符号）    |

## RAM账号所需权限

部署e-commerce-application，需要对部分阿里云资源进行访问和创建操作。因此您的账号需要包含如下资源的权限。
  **说明**：当您的账号是RAM账号时，才需要添加此权限。

| 权限策略名称                          | 备注                     |
|---------------------------------|------------------------|
| AliyunECSFullAccess             | 管理云服务器服务（ECS）的权限       |
| AliyunVPCFullAccess             | 管理专有网络（VPC）的权限         |
| AliyunROSFullAccess             | 管理资源编排服务（ROS）的权限       |
| AliyunComputeNestUserFullAccess | 管理计算巢服务（ComputeNest）的用户侧权限 |
| AliyunMongoDBFullAccess         | 管理云数据库服务（MongoDB）的权限 |

## 部署流程

1.访问e-commerce-application服务[部署链接](https://computenest.console.aliyun.com/service/instance/create/cn-hangzhou?type=user&ServiceId=service-772b0bae17ab4142bfc2)
，按提示填写部署参数：

![image.png](2.png)

2.参数填写完成后可以看到对应询价明细，确认参数后点击**下一步：确认订单**。

![image.png](3.png)

3.确认订单完成后同意服务协议并点击**立即创建**进入部署阶段。

![image.png](4.png)

4.等待部署完成后进入服务实例管理。

## e-commerce-application使用示例

1.等待部署完成后进入服务实例管理，点击MyStore后面链接，访问服务器部署的e-commerce应用。

![image.png](5.png)
![image.png](6.png)

2.注册管理帐户用来管理产品。

![image.png](7.png)

3.添加产品。本文以添加iPhone 13产品系列为例。

- iPhone 13 mini: https://github.com/alibabacloud-howto/solution-mongodb-labs/raw/main/e-commerce-application/images/iphone-13-mini-blue-select-2021.png
- iPhone 13: https://github.com/alibabacloud-howto/solution-mongodb-labs/raw/main/e-commerce-application/images/iphone-13-family-select-2021.jpeg
- iPhone 13 pro: https://github.com/alibabacloud-howto/solution-mongodb-labs/raw/main/e-commerce-application/images/iphone-13-pro-blue-select.png
- iPhone 13 pro max: https://github.com/alibabacloud-howto/solution-mongodb-labs/raw/main/e-commerce-application/images/iphone-13-pro-max-gold-select.png

![image.png](8.png)
![image.png](9.png)
![image.png](10.png)

4.模拟用户浏览，加入购物车并查看订单。

![image.png](11.png)
![image.png](12.png)
![image.png](13.png)


## 通过MongoKu访问应用后台MongoDB数据库

1.在控制台找到MongoDB连接地址

![image.png](14.png)
![image.png](15.png)

2.访问MongoKu链接，添加MongoDB连接URI作为服务器，通过MongoKu导航和管理这个在线商店电子商务web应用程序的数据。

> URI中的****替换为自己设置的密码

![image.png](16.png)
![image.png](17.png)


## 参考文档
https://github.com/alibabacloud-howto/solution-mongodb-labs/tree/main/e-commerce-application
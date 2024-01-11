# Seamless E-Commerce Application Setup and Launch

>**Disclaimers：**This service is provided by a third party, and we make every effort to ensure its security, accuracy, and reliability, but we cannot guarantee that it is completely free from failures, interruptions, errors, or attacks. Therefore, our company hereby declares that we make no representations, warranties or commitments regarding the content, accuracy, completeness, reliability, applicability, and timeliness of this service, and we are not liable for any direct or indirect losses or damages arising from your use of this service; For the third-party websites, applications, products, and services accessed by you through this service, you are not responsible for their content, accuracy, completeness, reliability, applicability, and timeliness. You shall bear the risks and responsibilities arising from the consequences of use on your own; We are not responsible for any losses or damages arising from your use of this service, including but not limited to direct, indirect, profit, goodwill, data or other economic losses, even if our company has been informed in advance of the possibility of such losses or damages; We reserve the right to modify this statement from time to time, so please regularly check this statement before using this service. If you have any questions or concerns about this statement or this service, please contact us.

## Overview

This e-commerce application serves as a demonstration of an online store, built with the Node.js Express framework.

## Billing instructions

The expenses on e-commerce application mainly involve：

- Selected vCPU and memory specifications
- System disk type and capacity
- Public network bandwidth
- Cloud database MongoDB specifications and storage space

## Deployment Architecture

<img src="1.png" width="1500" height="700" align="bottom"/>

## Parameter Description

| Parameter Group            | Parameter item          | illustrate                                                                                                                                           |
|----------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Service Instance           | Service Instance Name   | The name can be up to 64 characters in length, and can contain digits, letters, hyphens (-), and underscores (_). The name must start with a letter. |
|                            | Region                  | The region where the service instance is deployed.                                                                                                   |
|                            | Instance Charge Type    | Charge type for the service instance.                                                                                                                |
| ECS instance configuration | Instance Type           | ECS instance type                                                                                                                                    |
|                            | Instance Password       | Server login password, Length 8-30, must contain three(Capital letters, lowercase letters, numbers, ()`~!@#$%^&*_-+={}[]:;'<>,.?/ Special symbol in) |
| network configuration      | Availability Zone       | The availability zone where the ECS instance is located                                                                                              |
|                            | VPC ID                  | VPC where resources are located                                                                                                                      |
|                            | VSwitch ID              | The availability zone of the VSwitch                                                                                                                 |
| MongoDB configuration      | Instance specifications | The specifications of MongoDB instances that can be used in the availability zone                                                                    |
|                            | Storage                 | Instance Storage                                                                                                                                     |
|                            | Password                | Length 8-30, must contain three items (uppercase letters, lowercase letters, numbers, () `~! @ # $%^&*-+=&# 124; {} []:; '<>/ Special symbols in)    |

## Permissions required

Deploying this service instance requires accessing and creating some Alibaba Cloud resources. Therefore, your account needs to include permissions for the following resources.
  **Note**：You only need to add this permission when your account is a RAM account.

| Permission policy name             | Remarks                                                                         |
|------------------------------------|----------------------------------------------------------------------------|
| AliyunECSFullAccess                | Permission to manage cloud server service (ECS)                            |
| AliyunVPCFullAccess                | Permission to manage private network (VPC)                                 |
| AliyunROSFullAccess                | Permission to manage Resource Orchestration Service (ROS)                  |
| AliyunComputeNestUserFullAccess    | Manage user-side permissions for the ComputeNest service (ComputeNest)     |
| AliyunMongoDBFullAccess            | Manage permissions for cloud database services (MongoDB)                   |

## Deployment steps

1.Visit Deployment Link and fill in the deployment parameters as prompted:[Deployment link](https://computenest.console.aliyun.com/service/instance/create/cn-hangzhou?type=user&ServiceId=service-772b0bae17ab4142bfc2)

![image.png](2.png)

2.After filling in the deployment link parameters, you can see the corresponding inquiry details. After confirming the parameters, click**Next step: Confirm the order**.

![image.png](3.png)

3.After confirming the completion of the order, agree to the service agreement and click **Create Now** to enter the deployment phase.

![image.png](4.png)

4.Wait for deployment to complete before entering service instance management.

## e-commerce-application  Usage examples

1.After the deployment is completed, enter the service instance management and click on the link behind MyStore to access the e-commerce application deployed by the server.

![image.png](5.png)
![image.png](6.png)

2.Register a management account to manage products.

![image.png](7.png)

3.Add products. This article takes adding the iPhone 13 product series as an example.

- iPhone 13 mini: https://github.com/alibabacloud-howto/solution-mongodb-labs/raw/main/e-commerce-application/images/iphone-13-mini-blue-select-2021.png
- iPhone 13: https://github.com/alibabacloud-howto/solution-mongodb-labs/raw/main/e-commerce-application/images/iphone-13-family-select-2021.jpeg
- iPhone 13 pro: https://github.com/alibabacloud-howto/solution-mongodb-labs/raw/main/e-commerce-application/images/iphone-13-pro-blue-select.png
- iPhone 13 pro max: https://github.com/alibabacloud-howto/solution-mongodb-labs/raw/main/e-commerce-application/images/iphone-13-pro-max-gold-select.png

![image.png](8.png)
![image.png](9.png)
![image.png](10.png)

4.Simulate user browsing, add to shopping cart and view orders.

![image.png](11.png)
![image.png](12.png)
![image.png](13.png)


## Accessing the application backend MongoDB database through MongoKu

1.Find the MongoDB connection address on the console.

![image.png](14.png)
![image.png](15.png)

2.Visit the MongoKu link, add the MongoDB connection URI as the server, and navigate and manage the data of this online store e-commerce web application through MongoKu.

> Replace **** in the URI with the password you set yourself

![image.png](16.png)
![image.png](17.png)


## Reference documents
https://github.com/alibabacloud-howto/solution-mongodb-labs/tree/main/e-commerce-application
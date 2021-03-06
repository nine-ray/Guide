# nine-ray guide
@[TOC] 
## 统一返回数据格式
| 字段名        | 参数含义     | 类型   | 备注 |
| ------------- | ------------ | ------ | ---- |
| success            | 请求是否成功       | true/false |      |
| code     | 状态吗   | string |      |
| data     | 请求返回数据  | JSON   |      |
| message      | 请求返回消息 | string |      |

## 统一返回错误码
| code        | 类型     | 
| ------------- | ------------ | 
| 6009            | 未知错误       | 
| 6008     | token无效   | 
| 6001     | 注册手机号已经被使用  | 



## 1. user-service

### 1.1用户注册

#### 1.1.1请求地址
> http://ipaddress:8010/user/signUp

#### 1.1.2请求方式
> POST

#### 1.1.3 请求参数
| 参数名         |  含义       | 是否必须 | 数据类型 | 备注                                                           |
| -------------- | ------------- | -------- | -------- | -------------------------------------------------------------- |
| account      | 用户账户号    | 否       | string   |                                                                |
| password      | 密码    | 是      | string   |                                                       |
| phone      | 手机号    | 是      | string     | 

#### 1.1.4 返回数据
   [统一返回数据格式](#统一返回数据格式)
#### 1.1.5 错误码
| code        | 类型     | 
| ------------- | ------------ | 
| 5001     | 注册手机号已经被使用  | 

 ### 1.2用户登录
 
 #### 1.2.1请求地址
 > http://ipaddress:8010/user/login/common
 
 #### 1.2.2请求方式
 > POST
 
 #### 1.2.3 请求参数
 | 参数名         |  含义       | 是否必须 | 数据类型 | 备注                                                           |
 | -------------- | ------------- | -------- | -------- | -------------------------------------------------------------- |
 | account      | 用户账户号    | 是       | string   |                                                                |
 | password      | 密码    | 是      | string   |                                                       |
 
 #### 1.2.4 返回数据
| 字段名        | 参数含义     | 类型   | 备注 |
| ------------- | ------------ | ------ | ---- |
| success            | 请求是否成功       | true/false |      |
| code     | 状态吗   | string |      |
| data     | token  | string   |      |
| message      | 请求返回消息 | string |      |
   
 #### 1.2.5 错误码
 | code        | 类型     | 
 | ------------- | ------------ | 
 | 5001     | 密码错误  | 







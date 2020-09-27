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



### 1.1分类列表

#### 1.1请求地址
> http://ipaddress:8050/product/category/list

#### 1.2请求方式
> Get

#### 1.3 请求参数
| 参数名         |  含义       | 是否必须 | 数据类型 | 备注                                                           |
| -------------- | ------------- | -------- | -------- | -------------------------------------------------------------- |
| parentId      | 上级分类ID    | 是       | number   |   一级分类传-1                                                             |

#### 1.4 返回数据
   | 字段名        | 参数含义     | 类型   | 备注 |
   | ------------- | ------------ | ------ | ---- |
   | success            | 请求是否成功       | true/false |      |
   | code     | 状态吗   | string |      |
   | data     | 请求返回数据  | jsonArray   |      |
   | message      | 请求返回消息 | string |      |
  
> data 格式

| 字段名        | 参数含义     | 类型   | 备注 |
| ------------- | ------------ | ------ | ---- |
| name     | 分类名称   | string |      |
| level     | 分类级别  | number   |      |
| parentId      | 上级ID | number |      |
| parentName      | 上级名称 | string |      |

   
#### 1.5 错误码
| code        | 类型     | 
| ------------- | ------------ | 
| 5009     | 未知错误  | 

 
  
 ### 2.1 商品新增
 > http://ipaddress:8050/product/page
 
 ### 2.2请求方式
 > POST
 
 ### 2.3 请求参数
 | 参数名         |  含义       | 是否必须 | 数据类型 | 备注                                                           |
 | -------------- | ------------- | -------- | -------- | -------------------------------------------------------------- |
 | id      | 商品ID    | 否       | number   |    新增不传、修改传                                                            |
 | mainImageUrl      | 主图列表    | 是      | array   |                                                       |
 | detailImageUrl      | 详情图列表    | 是      | array   |
 | name      | spu名称    | 是      | array   |
 | type      | 商品类型（虚拟商品、真实商品、食品）    | 是      | string   |        VIRTUAL, ACTUAL, CATER
 | published      | 是否上架    | 否      | bool   |默认true
 | deleted      | 是否删除    | 否      | bool   | 默认false
 | categoryId      | 二级工业分类ID    | 是      | number   |
 | skus      | sku列表    | 是      | array   |
 
  > sku格式
 
  | 参数名         |  含义       | 是否必须 | 数据类型 | 备注                                                           |
  | -------------- | ------------- | -------- | -------- | -------------------------------------------------------------- |
  | id      | 商品sku ID    | 否       | number   |    新增不传、修改传                                                            |
  | code      | sku code     | 否      | string   |   新增不传、修改传                                                  |
  | productId      | spu ID    | 否      | number   | 新增不传、修改传
  | skuImageUrl      | sku图片    | 是      | array   |
  | name      |  规格名称   | 是      | string   |  
  | price      | sku价格    | 是      | number   |
  | quantity      | sku库存    | 是      | number   |                                                       

 ### 2.4 返回数据
   [统一返回数据格式](#统一返回数据格式)

   
 ### 2.5 错误码
 | code        | 类型     | 
 | ------------- | ------------ | 
 | 5009     | 未知  | 

 
 
 ### 3.1 商品分页查询
 > http://ipaddress:8050/product/save
 
 ### 2.2请求方式
 > POST
 
 ### 2.3 请求参数
 | 参数名         |  含义       | 是否必须 | 数据类型 | 备注                                                           |
 | -------------- | ------------- | -------- | -------- | -------------------------------------------------------------- |
 | name      | spu名称    | 否      | string   |模糊
 | type      | 商品类型（虚拟商品、真实商品、食品）    | 是      | string   |        VIRTUAL, ACTUAL, CATER
 | published      | 是否上架    | 否      | bool   |默认true
 | deleted      | 是否删除    | 否      | bool   | 默认false
 | categoryId      | 二级工业分类ID    | 是      | number   |
                                                        

 ### 2.4 返回数据
   | 字段名        | 参数含义     | 类型   | 备注 |
   | ------------- | ------------ | ------ | ---- |
   | success            | 请求是否成功       | true/false |      |
   | code     | 状态吗   | string |      |
   | data     | 请求返回数据  | JSONArray   |      |
   | message      | 请求返回消息 | string |      |

> data结果

| 字段名        | 参数含义     | 类型   | 备注 |
| ------------- | ------------ | ------ | ---- |
| id            | id       | number |      |
| code     | 商品code   | string |      |
| name     | 商品名称  | string   |      |
| displayPrice      | 展示价格 | string |  高低价    |
| hasStock      | 是否有货 | bool |      |
| type     | 商品分类  | string   |      |
| categoryId     | 商品工业分类ID  | number   |      |
| published      | 是否上架 | bool |      |
| deleted      | 是否删除 | bool |      |
| mainImageUrl     | 商品主图列表  | array   |  展示第一张    |
| totalSales     | 销售总数  | number   |      |

   
 ### 2.5 错误码
 | code        | 类型     | 
 | ------------- | ------------ | 
 | 5009     | 未知  |





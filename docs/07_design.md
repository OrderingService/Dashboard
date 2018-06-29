---

layout: default
title: Design（设计）

---

# Design（设计）
{:.no_toc}

* 目录
{:toc}
</br>

## 7.1 UI Design（UI设计）

- 基本流程所对应的小程序界面（截图于 v1.0.0 版本）

  - 顾客在菜单界面进行点餐，所选菜品加至购物车
  
  ![菜单界面](https://raw.githubusercontent.com/OrderingService/WechatApplet/master/ScreenShots_v1.0.0/screenshot_1_frame.png)

  - 顾客确认购物车内的菜品，系统根据菜单生成应付金额
  
  ![购物车内容](https://raw.githubusercontent.com/OrderingService/WechatApplet/master/ScreenShots_v1.0.0/screenshot_2_frame.png)

  - 顾客付款，系统处理支付
  
  ![进行付款](https://raw.githubusercontent.com/OrderingService/WechatApplet/master/ScreenShots_v1.0.0/screenshot_3_frame.png)

  - 系统记录完整的订单信息，并把信息发送到账务系统
  
  ![生成订单](https://raw.githubusercontent.com/OrderingService/WechatApplet/master/ScreenShots_v1.0.0/screenshot_4_frame.png)

</br>

## 7.2 Database Design（数据库设计）

### 7.2.1 用户及权限系统数据库设计

- 角色设计
  - 顾客角色
  - 商家角色
- 模块设计
  - 菜单模块：按照分类，显示当前可售的全部菜品名、菜品图像、菜品定价。顾客可通过点击“+”购买菜品，商家可完成对菜品的增删改操作
  - 购物车模块：用户在菜单模块选择菜品并添加进购物车，购物车中会显示当前选择的菜品名和菜品数量，以及每个菜品的总价，购物车模块最下会显示当前购买菜品的总金额。同时，顾客可以在购物车模块中通过“+”、“-”按键完成对菜品数量的修改
  - 订单模块：显示订单详情，包括订购菜品的名字、数量和总价，以及订单总计金额。同时，顾客可以在“备注”区填写对菜品的自定义要求。支付完成后，会生成取餐码，同时返回订单号和订单时间，给顾客显示
  - 后厨模块：显示每个订单的菜品名和数量
  
- 访问权限设计
  - 顾客可访问菜单模块，购物车模块，订单模块
  - 商家可访问菜单模块和后厨模块

- 操作权限设计
  - 顾客登陆后，可以完成点餐、支付，按取款码取餐
  - 商家登陆后，可以完成对菜品增删查改，同时能获取订单中的菜品和数量信息
<br/>

#### E-R Logical Model（E-R逻辑图）

![](https://raw.githubusercontent.com/OrderingService/Dashboard/gh-pages/imgs/er_model.png)

如上图所示，本应用中共存在着七个实体，分别是customer，menu，EDish，EOrder，dish-to-order，cook，Bissness Man. 其中，customer以ID，用户名，桌号为键，以ID为主键；menu是菜单实体集，以ID为主键；EDish是菜品实体集，以菜品名，菜品图像，菜品受欢迎级别，菜品种类，菜品评论，是否可获得，当前定价，原始定价为键；Eorder为订单实体集，以付款方式，订单总价，订单状态，订单创建时间，订单支付时限为键；dish-to-dish实体集针对后厨，以菜品名和菜品数量为键；cook是厨师实体集，以ID为主键；Bussiness Man以电话号为实体集。
<br/> 
此外，实体之间的关系已经在图中标出，实体边上的1或N反应其映射关系。
<br/>

### 7.2.2 PML点餐子系统数据库设计
具体的Menu（菜单）与Order（订单）数据库设计

![](https://raw.githubusercontent.com/OrderingService/Dashboard/gh-pages/imgs/database.png)

## 7.3 API Design


API  Design

Host：http://172.18.146.154:8080

### 用例 1 ：查看菜单

场景：用户通过扫码进入小程序，需要展示点餐系统的菜单

##### Request

 ``` 
 Url：/test/Select?func=getMenu
 Parameters：无
 Method：GET
 Header: {'Accept': 'application/json'}
``` 
 
#### Respond 

> example
``` 
 {
    [
      {
        "type": "开胃美味",
        "image_url": "../../images/foods/appetizer5.jpg",
        "name": "和风披萨（照烧鸡）",
        "price": 28
      },
 ......
    ]
}
``` 


### 用例 2 ：提交订单

场景：用户支付成功，向商家提交订单，返回取餐号

#### Request
``` 
 Url：/test/Insert?func=createOrder
 Parameters ↓
 data: {
 	userName: app.globalData.userInfo.nickName,
 	price: wx.getStorageSync('sumMoney'),
 	dishArray: JSON.stringify(wx.getStorageSync('cartList'))
 }
 Method：POST
 Header: {'Accept': 'application/json'}
 ``` 
#### Respond 
> example
``` 
{
	"orderNum": 201806052300302978,
	"objectId": "b8",
	"userName": "王小明",
	"price": 42,
	"dishArray": 
[{"index":2,"name":"抹茶海鲜杯面","price":12,"number":1},{"index":4,"name":"明太子乌冬面","price":15,"number":2}]
	"createDate": 2018-06-05 22：59:07,
	"updateDate": 2018-06-05 22：59:07,
  }
  ``` 
！注：将body中实时生成的orderNum、objectId、createDate返回给用户。
<br/>

## 7.4 Software Architecture Doucument

## 7.5 Usecase design

 - ECB的顺序图

![](https://raw.githubusercontent.com/OrderingService/Dashboard/gh-pages/imgs/ECBSequence.png)

 - ECB的类图

![](https://raw.githubusercontent.com/OrderingService/Dashboard/gh-pages/imgs/ECBClass.png)

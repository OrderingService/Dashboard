---

layout: default
title: Design（设计）

---

# Design（设计）

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
- 访问权限设计

E-R Logical Model（E-R逻辑图）

![](https://raw.githubusercontent.com/OrderingService/Dashboard/gh-pages/imgs/er_model.png)

如上图所示，本应用中共存在着七个实体，分别是customer，menu，EDish，EOrder，dish-to-order，cook，Bissness Man. 其中，customer以ID，用户名，桌号为键，以ID为主键；menu是菜单实体集，以ID为主键；EDish是菜品实体集，以菜品名，菜品图像，菜品受欢迎级别，菜品种类，菜品评论，是否可获得，当前定价，原始定价为键；Eorder为订单实体集，以付款方式，订单总价，订单状态，订单创建时间，订单支付时限为键；dish-to-dish实体集针对后厨，以菜品名和菜品数量为键；cook是厨师实体集，以ID为主键；Bussiness Man以电话号为实体集。
此外，实体之间的关系已经在图中标出，实体边上的1或N反应其映射关系。

### 具体的Menu（菜单）与Order（订单）数据库设计

![](https://raw.githubusercontent.com/OrderingService/Dashboard/gh-pages/imgs/database.png)

## 7.3 API Design

## 7.4 Software Architecture Doucument

## 7.5 Usecase design

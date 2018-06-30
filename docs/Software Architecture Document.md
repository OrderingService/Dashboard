## Software Architecture Document

| 版本 | 日期 | 描述 | 作者|
| -- | -- | -- | -- |
| 1.0 | 2018.6.25 | 架构问题、解决方案说明、逻辑视图、物理视图 | awm |

### 架构设计
 
前后端分离开发，前端使用微信小程序的前端设计工具实现，将数据表单post到tomcat服务器，服务器获取数据后进行适当处理然后将数据存储到数据库中。数据库采用
 MySQL实现。

### 解决方案说明

### 逻辑视图

![逻辑视图](https://github.com/OrderingService/Dashboard/blob/gh-pages/imgs/package_diagram.png)

### 物理视图

![物理视图](https://github.com/OrderingService/Dashboard/blob/gh-pages/imgs/Physical_view.png)

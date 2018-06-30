## Software Architecture Document

| 版本 | 日期 | 描述 | 作者|
| -- | -- | -- | -- |
| 1.0 | 2018.6.25 | 架构问题、解决方案说明、逻辑视图、物理视图 | awm |

### 架构设计
 
前后端分离开发，前端使用微信小程序的前端设计工具实现，将数据表单post到tomcat服务器，服务器获取数据后进行适当处理然后将数据存储到数据库中。数据库采用
 MySQL实现。

### 解决方案说明
问题：无法有效利用服务器的多核计算资源
 
解决方案：服务器采用Docker部署，因此可以快速部署多个服务器实例，每个实例监听不同的端口。

通过服务发现机制，统计所有已启动的服务器实例，并自动配置Nginx进行均衡负载。

### 逻辑视图

![逻辑视图](https://github.com/OrderingService/Dashboard/blob/gh-pages/imgs/package_diagram.png)

### 物理视图

![物理视图](https://github.com/OrderingService/Dashboard/blob/gh-pages/imgs/Physical_view.png)

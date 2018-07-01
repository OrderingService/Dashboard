---

layout: default
title: 15310022-FinalReport

---
# FinalReport
{:.no_toc}

* 目录
{:toc}

## 课程学习自我总结

这是我第一次正经地去完成一个github上的团队开发项目，在这个过程中学到了很多开发上的技术与规范。
重点聊一下技术上的收获，在开发前端的过程中更新购物车中对象的储存结构，允许修改菜品的数目；增加减号icon，可以修改菜品的数目；更新部分页面的布局，使用rpx解决自适应问题；在跳转支付的按钮处增加手动授权，解决无法获得userInfo的问题；使用scroll回调，允许菜单左边侧栏中选中的标签随右边菜单栏的划动改变，在某些分辨率下仍存在错位现象。为了更深刻地理解小程序的前端开发，特意将其与其他一些框架做了对比。鉴于开发人数上的限制，暂未完成商户端前端的开发。在后端开发中，选择了tomcat 9.0.8-jre8，其中的重点是通过jdbc对数据库使用进行封装，我们需要将前端发回的request与json数据进行解析。后期添加了nginx作为代理服务器，实现服务器的分流负载，本想实现redis作为数据库异步更新的cache，但由于一个人的工作效率有限且工作量较大，暂时没有时间去实现。在docker-compose的搭建中，由于个人疏忽，服务器使用的系统为mac os，一时间没办法找到合适的docker基础镜像，故docker的某些容器可能会存在问题。
最后特别感谢johnny-law同学有关docker搭建的博客，虽然同样由于时间不足，我暂时仍未很好地掌握这个技术，在未来的时间将会完善这一部分的内容。此外也要感谢vector同学对于在eclipse上搭建tomcat的帮助。

## PSP 2.1 统计表

| PSP2.1          | Personal Software Process Stages | Time(%) |
|-----------------|----------------------------------|---------|
|**Planning**       |	**计划**	                         |	**5**	|
|● Estimate         |	估计这个任务需要多长时间             |	5	|
|**Develoment**     |	**开发**                          |	**90**	|
|● Analysis         |	需求分析（包括学习新技术）            |	5	|
|● Design Spec      |	生成设计文档                        |	3	|
|● Design Review    |	设计复审（和同事审核设计文档）         |	3    |
|● Coding Standard  |	代码规范（为目前的开发制定规范）       |	3    |
|● Design           |	具体设计                           |	20   |
|● Coding           |	具体编码                           |	31   |
|● Coding Review    |	代码复审                           |	10   |
|● Test             |	测试（自我测试，修改代码，提交修改）    |	15   |
|**Reporting**      |	**报告**                          |	**5**    |
|● Test Report      |	测试报告                           |	2    |
|● Size Measurement |	计算工作量                         |	1       |
|● Postmortem & Process Improvement Plan|	事后总结，并提出过程改进计划|	2|

## 个人分支的 GIT 统计报告

![](https://raw.githubusercontent.com/Eros-L/Eros-L.github.io/master/_posts/image/contribution.png)

[备注说明]
由于前期项目路径没搞好，导致了大量的commit记录，实际上多为名字或路径的修改。同时也大量上传了重复的内容。

## 自认为最得意/或有价值/或有苦劳的工作清单

1. 对前端功能上的完善
2. 参与数据库设计
3. 完成后端搭建，虽然仍存在很多不足

## 个人的技术类、项目管理类博客清单

1. [Eclipse下Tomcat+Nginx+Java部署](https://eros-l.github.io/share/2018/07/01/blog-share/)

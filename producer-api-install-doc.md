# 数据提供方-数据服务 API 部署文档

## 引言

数据服务 api 是基于 http[s] 协议的一个数据服务端服务。它给数据供应方提供了一种方便的内部数据访问的可靠服务，成功实现了一组以模型计算为核心的数据处理，多方计算混淆数据的业务过程，并且提供了一组 restful API 风格的简单接口

## 如何部署

* 自行搭建服务器
* 安装 jdk，版本 1.8 +
* [下载数据服务 jar 包](https://github.com/unitedata-org-public/UD-Release/blob/master/ud-data-producer)
* 解压包文件到指定的路径，并配置参数，具体配置请查看数据服务配置
* 使用 jdk 运行下载的 jar 包
* 打开浏览器，输入地址 http://{域名}/swagger-ui.html，看到下图

![WX20180807-172916_2x](WX20180830-162713@2x.png)

## 数据服务配置

数据服务可配置内容：

* account=合约访问账户
* privateKey=合约访问账户私钥
* contractApi=合约 API 访问地址
* edsApi=企业内部系统 API 访问地址
* multiServiceApi=当前节点多方计算 API 访问地址
* timeoutRead=一次多方计算网络数据读取超时时间，单位毫秒。默认 5000
* timeoutConnect=一次多方计算网络连接超时时间，单位毫秒。默认 3000
* timeoutReply=一次多方计算数据交换响应时间，单位毫秒。默认 15

数据服务的配置信息通过三种方式获取，优先级依次提高，操作系统环境变量的优先级最高：

* 应用配置文件 application.properties
* 外部应用文件 /{path}/application.properties
* 操作系统环境变量

### 自定义外部配置

外部配置文件使用 peoperties 文件

默认的外部配置文件路径为：/usr/local/config/application.properties

可以通过设置操作系统环境变量 propertiesFileName 来改变外部配置文件的路径

# 第1章 大数据概述
## 1-5 什么是大数据以及大数据的4V特征
数据量             			Volume
多样性，复杂性    			Variety
速度                 			Velocity
基于高度分析的新价值 		Value

## 1-6 大数据带来的技术变革

大数据带来的技术变革
	技术驱动：数据量大
		存储：文件存储 ==> 分布式存储
		计算：单机    ==> 分布式计算
		网络：万兆
		DB： RDBMS  ==> NoSQL(HBase/Redis....)

​	商业驱动

## 1-7 大数据现存的模式

* 手握大数据，没有大数据思维
* 没有大数据，有大数据思维
* 既有大数据，又有大数据思维 

## 1-8 大数据的技术概念

* 数据采集：Flume Sqoop
* 数据存储：Hadoop
* 数据处理、分析、挖掘：Hadoop、Spark、Flink....
* 可视化：

## 1-9 大数据带来的挑战

* 对现有数据库管理技术的挑战
* 经典数据库技术并没有考虑数据的多类别
* 实时性的技术挑战
* 网络架构、数据中心、运维的挑战
* 数据隐私、防止泄露
* 数据源复杂多样

## 1-10 如何对大数据进行存储和分析

* Google只发表了技术论文，并没有开放源代码
* 一个模仿Google大数据技术的开源实现来了

# 第2章 初识Hadoop 
## 2-2 Hadoop概述

Apache社区的顶级项目：xxxx.apache.org
	hadoop.apache.org
	hive.apache.org
	hbase.apache.org
	spark.apache.org
	flink.apache.org
	storm.apache.org

*  Hadoop是一个分布式的系统基础架构

  分布式文件系统：HDFS实现将文件分布式存储在很多的服务器上
  分布式计算框架：MapReduce实现在很多机器上分布式并行计算
  分布式资源调度框架：YARN实现集群资源管理以及作业的调度

## 2-3 Hadoop核心组件之HDFS概述

* 源自于Google的GFS论文，论文发表于2003年10月
* HDFS是GFS的克隆版
* HDFS特点：扩展性&容错性&海量数据存储
* 将文件切分成指定大小的数据块并以多副本的存储在多个机器上
* 数据切分、多副本、容错等操作对用户是透明的 

## 2-4 Hadoop核心组件之MapReduce

* 源自于Google的MapReduce论文，论文发表于2004年12月
* MapReduce是Google MapReduce的克隆版
* MapReduce特点：扩展性&容错性&海量数据离线处理

## 2-5 Hadoop核心组件之YARN

* YARN：Yet Another Resource Negotiator

* 负责整个集群资源的管理和调度 
* YARN特点：扩展性&容错性&多框架资源统一调度

## 2-6 Hadoop优势

* 高可靠性

  数据存储：数据块多副本

  数据计算：重新调度作业计算

* 高扩展性

  存储/计算资源不够时，可以横向的线性扩展机器

  一个集群中可以包含数以千计的节点

* 其他

  存储在廉价机器上，降低成本

  成熟的生态圈

## 2-7 Hadoop发展史

[Hadoop 十年解读与发展预测](https://www.infoq.cn/article/hadoop-ten-years-interpretation-and-development-forecast)

## 2-8 Hadoop生态圈

* 狭义Hadoop VS 广义Hadoop

  狭义Hadoop：是一个适合大数据分布式存储（HDFS）、分布式计算（MapReduce）和资源调度（YARN）的平台

  广义Hadoop：指的是Hadoop生态系统，Hadoop生态系统是一个很庞大的概念，Hadoop是其中最重要最基础的一个部分；生态系统中的每一子系统只解决某一个特定的问题域（甚至可能很窄），不搞统一型的一个全能系统，而是小而精的多个小系统

* Hadoop生态系统的特点

  开源、社区活跃

  囊括了大数据处理的方方面面

  成熟的生态圈

## 2-9 Hadoop发行版选型

常用的Hadoop发行版
	Apache
		优点：纯开源
		缺点：不同版本/不同框架之间整合 jar冲突... 吐血

​	CDH：https://www.cloudera.com/   60-70%
​		优点：cm(cloudera manager) 通过页面一键安装各种框架、升级、支持impala
​		缺点：cm不开源、与社区版本有些许出入

​	Hortonworks：HDP  企业发布自己的数据平台可以直接基于页面框架进行改造
​		优点：原装Hadoop、纯开源、支持tez
​		缺点：企业级安全不开源

​	MapR

## 2-10 OOTB环境的使用

VMvare打开hadoop000.rar中的hadoop000.vmx

密码123456

```shell
sudo -i
cd /etc/sysconfig/network-scripts
rm ifcfg-lo
ip addr # 复制物理地址
vi ifcfg-eth0
#物理地址修改
#配置ip和gateway

vi /etc/sysconfig/network #配置主机名
vi /etc/resolv.conf #配置nameserver
reboot
ping www.baidu.com
ssh hadoop@192.168.199.233 #远程操作
```

# 第3章 分布式文件系统HDFS
## 3-1 HDFS概述
## 3-2 HDFS设计目标
## 3-3 HDFS架构详解
## 3-4 文件系统NameSpace详解
## 3-5 HDFS副本机制
## 3-6 本课程使用的Linux环境介绍
## 3-7 Hadoop部署前置介绍
## 3-8 JDK1.8部署详解
## 3-9 ssh无密码登陆部署详解
## 3-10 Hadoop安装目录详解及hadoop-env配置
## 3-11 HDFS格式化以及启动详解
## 3-12 HDFS常见文件之防火墙干扰
## 3-13 Hadoop停止集群以及如何单个进程启动
## 3-14 Hadoop命令行操作详解
## 3-15 深度剖析Hadoop文件的存储机制
## 3-16 HDFS API编程之开发环境搭建
## 3-17 HDFS API编程之第一个应用程序的开发
## 3-18 HDFS API编程之jUnit封装
## 3-19 HDFS API编程之查看HDFS文件内容
## 3-20 HDFS API编程之创建文件并写入内容
## 3-21 HDFS API编程之副本系数深度剖析
## 3-22 HDFS API编程之重命名
## 3-23 HDFS API编程之copyFromLocalFile
## 3-24 HDFS API编程之带进度的上传大文件
## 3-25 HDFS API编程之下载文件
## 3-26 HDFS API编程之列出文件夹下的所有内容
## 3-27 HDFS API编程之递归列出文件夹下的所有文件
## 3-28 HDFS API编程之查看文件块信息
## 3-29 HDFS API编程之删除文件
## 3-30 HDFS项目实战之需求分析
## 3-31 HDFS项目实战之代码框架编写
## 3-32 HDFS项目实战之自定义上下文
## 3-33 HDFS项目实战之自定义处理类实现
## 3-34 HDFS项目实战之功能实现
## 3-35 HDFS项目实战之使用自定义配置文件重构代码
## 3-36 HDFS项目实战之使用反射创建自定义Mapper对象
## 3-37 HDFS项目实战之可插拔的业务逻辑处理
## 3-38 HDFS Replica Placement Policy
## 3-39 HDFS写数据流程图解
## 3-40 HDFS读数据流程图解
## 3-41 HDFS Checkpoint详解
## 3-42 HDFS SaveMode

# 第4章 分布式计算框架MapReduce
## 4-1 课程目录
## 4-2 MapReduce概述
## 4-3 MapReduce编程模型详解
## 4-4 MapReduce编程模型核心概念详解
## 4-5 词频统计之自定义Mapper实现
## 4-6 词频统计之自定义Reducer实现
## 4-7 词频统计之自定义Driver类实现
## 4-8 词频统计之本地方式运行
## 4-9 词频统计之通过Debug方式进一步了解偏移量以及重构代码
## 4-10 词频统计升级之Combiner操作 试看
## 4-11 流量统计实战之需求
## 4-12 流量统计实战之自定义复杂数据类型
## 4-13 流量统计实战之自定义Mapper类
## 4-14 流量统计实战之自定义Reducer实现
## 4-15 流量统计实战之Driver开发
## 4-16 流量统计实战之代码重构及NullWritable的使用
## 4-17 流量统计实战升级之自定义Partitioner

# 第5章 资源调度框架YARN
## 5-1 课程目录
## 5-2 YARN产生背景
## 5-3 YARN概述
## 5-4 YARN架构详解
## 5-5 YARN执行流程
## 5-6 YARN环境部署
## 5-7 提交example案例到YARN上运行
## 5-8 提交流量统计案例到YARN上运行

# 第6章 电商项目实战Hadoop实现
## 6-1 课程目录
## 6-2 用户行为日志概述
## 6-3 为什么要记录用户行为日志
## 6-4 日志内容介绍
## 6-5 用户行为日志分析的意义所在
## 6-6 电商常用术语
## 6-7 项目需求描述
## 6-8 数据处理流程及技术架构
## 6-9 浏览量统计功能实现
## 6-10 省份浏览量统计之IP库解析
## 6-11 省份浏览量统计之日志解析
## 6-12 省份浏览量统计之功能实现
## 6-13 页面浏览量统计之页面编号获取
## 6-14 页面浏览量统计之功能实现
## 6-15 数据处理过程中ETL的重要性
## 6-16 原始日志ETL操作
## 6-17 浏览量统计功能升级
## 6-18 省份浏览量统计功能升级
## 6-19 页面浏览量统计功能升级思路
## 6-20 打包到服务器上运行
## 6-21 项目扩展

# 第7章 数据仓库Hive
## 7-1 课程目录
## 7-2 Hive产生背景
## 7-3 Hive是什么
## 7-4 为什么要使用Hive
## 7-5 Hive在Hadoop生态圈中的位置
## 7-6 Hive体系架构
## 7-7 Hive部署架构
## 7-8 Hive与RDBMS的区别
## 7-9 Hive部署
## 7-10 Hive快速入门
## 7-11 Hive DDL之数据库操作
## 7-12 Hive DDL之表操作
## 7-13 Hive DML之加载和导出数据
## 7-14 Hive QL基本统计
## 7-15 Hive QL之聚合函数
## 7-16 Hive QL之分组函数
## 7-17 Hive QL之join的使用
## 7-18 Hive QL执行计划

# 第8章 电商项目实战Hive实现
## 8-1 课程目录
## 8-2 外部表在Hive中的使用
## 8-3 track_info分区表的创建
## 8-4 将ETL的数据加载到Hive表
## 8-5 使用Hive完成统计分析功能
## 8-6 Hive实现项目的方便性体现

# 第9章 Hadoop分布式集群搭建
## 9-1 课程目录
## 9-2 Hadoop集群规划
## 9-3 前置条件安装
## 9-4 JDK安装
## 9-5 Hadoop集群部署
## 9-6 提交作业到Hadoop集群上运行
## 9-7 课程总结
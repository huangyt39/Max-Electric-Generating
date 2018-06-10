## 概述
用mapreduce的方法在hadoop平台上，在数据文件中筛选出广东省2007年-2017年中，每一年发电量最高的月份的发电量

## 运行
### 1.配置JDK，安装hadoop
### 2.启动并验证hadoop
    /usr/local/hadoop/sbin/start-dfs.sh 
    /usr/local/hadoop/sbin/start-yarn.sh
    jps
### 3.在hdfs 上创建输入文件夹MaxEleInput，并把数据文件放进去
    /usr/local/hadoop/bin/hdfs dfs -mkdir /MaxEleInput
    /usr/local/hadoop/bin/hdfs dfs -put GenerateEleData.txt /MaxEleInput(在Generation.txt所在目录下)
### 4.运行MaxEle程序
    /usr/local/hadoop/bin/hadoop jar MaxEle /MaxEleInput /MaxEleOutput(在jar包所在目录下)
### 5.查看输出文件及其结果
    /usr/local/hadoop/bin/hdfs dfs -cat /MaxEleOutput/*
浏览器进入http://192.168.142.128(masterip地址):50070/explorer.html#/output可以查看文件

## 参考资料
### 数据来源
http://data.stats.gov.cn/easyquery.htm?cn=E0101
### 参考书目
《Hadoop权威指南》

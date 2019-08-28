# 服务器交接
## 服务器 ip 与主机名
1. 192.168.1.83 - data1 简称 83
2. 192.168.1.84 - data2 简称 84
3. 192.168.1.71 - data3 简称 71
4. 192.168.1.72 - data4 简称 72
5. 192.168.1.73 - data5 简称 73
## 各服务器账号密码
### 83 服务器
    userName: root
    passwd: Mnw2019Q3

    userName: hadoop
    passwd: 123456
### 84 服务器
    userName: root
    passwd: Mnw!@#2018Q4

    userName: hadoop
    passwd: 123456

    userName: fengkong
    passwd: fengkong

#### 60-62
    userName: root
    passwd: 123456

    userName: hadoop
    passwd: 123456
### 71-73 服务器
    userName: root
    passwd: Mnw!@#2019Q2

    userName:hadoop
    passwd: 123456

    userName:fengkong
    passwd:fengkong
## 数据库账号密码
### 83 MySQL
    userName: root@localhost
    passwd: Mnw!@#456

    userName:admin@%
    passwd: Mnw!@#456

    userName: bo.chao@%
    passwd: Mnw!2018

    userName: dawei.chen@%
    passwd: Mnw!2018@

    userName: fengkong@%
    passwd: Mnw!2018
    
### 其他 Docker MySQL
    userName: root@%
    passwd: 123456

## 服务器服务分布
### 83 服务器
1. MySQL 存储库
2. Tomcat 服务
3. Docker-canal 消费端

### 84 服务器
1. Docker-60 Hadoop 主节点
2. Docker-61 HBase 主节点 -未启动
3. Docker-62 Hive 主节点
4. Kafka 服务
   
### 71 服务器
1. Hadoop 主节点
### 72 服务器
1. HBase 主节点
### 73 服务器
1. Hive 主节点
2. Spark 主节点
3. Docker-gitlab-runner_runner_1 服务
4. Docker-hive_mysql 服务器



https://archive.cloudera.com/cdh5/cdh/5/
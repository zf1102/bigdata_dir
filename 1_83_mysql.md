32g内存  1T固态 + xT机械  6核12线程


# 83_MySQL 
## 服务器地址
1. ip: 192.168.1.83
2. hostName: data1
3. user: root
4. passwd: Mnw!@#2019Q3

## 数据库管理帐号
### root@localhost
    passwd: Mnw!@#456

### admin@%
    passwd: Mnw!@#456

### bo.chao@%
    passwd: Mnw!2018
### chaoyu.huang@%
    passwd: Mnw!2018
### dawei.chen@%
    passwd: Mnw!2018@
### fengkong@%
    passwd: fengkong

## 服务器重启之后
1. 用 ` systemctl status mysqld` 查看 MySQL 服务运行状态
2. 如果为非运行状态 `systemctl start mysqld` 启动服务

## MySQL 核心参数

### 最大线程数
innodb_thread_concurrency=24
### 缓存,索引和数据的内存大小
innodb_buffer_pool_size=4G
### 磁盘处理运行方式
innodb_flush_method=O_DIRECT
### 刷新脏页数量
innodb_io_capacity=5000
### 自适应，探测内存等 innodb_buffer_pool_size innodb_log_file_size  innodb_flush_method 
innodb_dedicated_server=ON
### innodb双写
innodb_doublewrite=OFF
### sql 模式 一些格式数据的限定
sql_mode=
### 自适应刷新(会根据重做日志 ib_logfile 生成的速度和刷新频率来将脏页刷入磁盘)
innodb_adaptive_flushing=ON
### 查询 information_schema 库的表时，随机提取其他库的每个表索引数据
innodb_stats_on_metadata=OFF
### 
innodb_change_buffering=all
### 服务器连接最多等待时长服务器在关闭非交互式连接之前等待活动的秒数
wait_timeout=31536000
### 服务器在关闭之前等待交互式连接上的活动的秒数连接关闭后保存时间长度
interactive_timeout=31536000
### 
max_allowed_packet=2000M
max_sort_length=8388608
sort_buffer_size=256M
max_length_for_sort_data=8388608
read_buffer_size=256M
join_buffer_size=256M
read_rnd_buffer_size=256M
innodb_sort_buffer_size=64M
max_connections=2000
innodb_default_row_format=Compact
innodb_file_per_table=1
innodb_flush_log_at_trx_commit=0
local_infile=1
expire_logs_days=1
tmp_table_size=512M

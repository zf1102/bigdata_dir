# ZOOKEEPER 基本原理
## 角色
|           角色                |                           描述                              |
|------------------------------|---------------------------------------------------------------|
|    领导者(Leader)             |领导者负责进行投票的发起和决议，更新系统状态                      |
|学习者.跟随者(Learner.Follower)|Follwer 用于接收客户端请求并向客户端返回结果，在选举过程中参与投票   |
|学习者.观察者(Learner.ObServer)|ObServer 可以接收客户端连接，将写请求转发给 Leader 节点。但 ObServer 不参与投票过程，只同步 Leader 的状态。ObServer 的目的是为了扩展系统，提高读取速度。                    |
|     客户端(Client)            |      请求发起                                                  |


## 选举流程
### Basic Paxos 选举流程
选主的具体流程图如下所示：
![mehmc9.png](https://s2.ax1x.com/2019/08/16/mehmc9.png)

通过流程分析我们可以得出：要使Leader获得多数Server的支持，则Server总数必须是奇数2n+1，且存活的Server的数目不得少于n+1.

每个Server启动后都会重复以上流程。在恢复模式下，如果是刚从崩溃状态恢复的或者刚启动的server还会从磁盘快照中恢复数据和会话信息，zk会记录事务日志并定期进行快照，方便在恢复时进行状态恢复。

### Fast Paxos 选举流程
某Server首先向所有Server提议自己要成为leader，当其它Server收到提议以后，解决epoch和zxid的冲突，并接受对方的提议，然后向对方发送接受提议完成的消息，重复这个流程，最后一定能选举出Leader。其流程图如下所示：
![meIHgg.png](https://s2.ax1x.com/2019/08/16/meIHgg.png)
### 工作流程

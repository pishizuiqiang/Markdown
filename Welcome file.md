## 数据库


```mermaid
graph TB
shiwu(事务管理)-->mvcc(MVCC)
shiwu-->suo(加锁)
mvcc---gong{共同实现}
suo---gong
gong-->result(一致性非阻塞读)
```
[数据库事务特征、数据库隔离级别](https://www.jianshu.com/p/fd51cb8dc03b)

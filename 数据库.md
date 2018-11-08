## 数据库


```mermaid
graph TB
shiwu(事务管理)-->mvcc(MVCC)
shiwu-->suo(加锁)
mvcc---gong{共同实现}
suo---gong
gong-->result(一致性非阻塞读)




```

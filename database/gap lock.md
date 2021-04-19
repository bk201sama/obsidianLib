# gap
gap就是索引树中插入新记录的空隙
# gap锁
加在gap上的锁，还有一个next-key锁，是记录+记录前面的gap的组合的锁。作用是防止幻读。通过锁阻止特定条件的新记录的插入，因为插入时也要获取gap锁(Insert Intention Locks)。只在REPEATABLE READ或以上的隔离级别下的特定操作才会取得gap lock或nextkey lock。为保证两次当前读返回一致的记录，那就需要在第一次当前读与第二次当前读之间，其他的事务不会插入新的满足条件的记录并提交。为了实现这个功能，GAP锁应运而生，如下图锁住b+树的3个gap
![](https://images2015.cnblogs.com/blog/569491/201605/569491-20160531130411383-483975821.jpg)
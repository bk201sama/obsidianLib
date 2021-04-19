# intro
innodb 行级锁
1.  record lock
锁住某一记录
2. [[gap lock]]
锁住某一段范围中的记录
3. next key lock
前2者的叠加

# use
只有在REPEATABLE READ或以上的隔离级别下的特定操作才会取得gap lock或nextkey lock。locking reads（悲观锁`select for update or 
 LOCK IN SHARE MODE` lock in share mode适用于两张表存在业务关系时的一致性要求，for  update适用于操作同一张表时的一致性要求）,update,lock或nextkey锁
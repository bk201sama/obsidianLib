# Structure
是一个范型[[interface]]，继承自[[Iterable]],说明是一个可遍历的接口

## size
返回集合的大小

## isEmpty
返回是否为空

## contains
返回是否包含元素

## iterator
返回遍历器

## toArray
返回数组

## add
添加对象，如果重复返回false

## remove
如果对象存在返回true

## containsAll
如果存在所以元素返回true

## removeAll
如果集合改变了返回false

## default removeIf
条件删除，如果集合改变返回true

## retainAll
得到交集，如果集合未改变，返回true，否则false

## clear
清空集合

## equals
集合是否相等

## hashCode
返回hash int值

## default spliterator
返回并行遍历器

## default stream
返回stream

## default parallelStream
返回Stream


# Structure
继承自[[Collection]]的[[interface]]

## size,isEmpty,contains,iterator,toArray,add,remove,containsAll,addAll,removeAll,retainAll,clear,equals,hashCode,spliterator 
和[[Collection]]类似，重载了一些方法，增加了index参数。比如add，remove,addAll，spliterator传入了ORDERED

## default replaceAll
入参function一元子类UnaryOperator

## default sort
利用[[Arrays]]的sor方法排序，然后替换list值

## get，set 
入参index

## indexOf
返回搜索元素的位置，不存在返回-1

## lastIndexOf
返回最后的元素位置，不存在返回-1

## listIterator
返回list迭代器，入参可以传入index

## subList
返回的是原list的视图，区间前闭后开

## default spliterator
分片迭代器





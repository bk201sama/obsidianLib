# Structure
是一个范型[[interface]]

 ## tryAdvance
  存在处理并返回true，否则返回false。使用情景while(tryAdance){...}
  
  ### trySplit
  分拆遍历序列，返回Spliterator类，返回的是分割出来的那一部分数据，直至分不出来返回null
  
  ## estimateSize
  返回long，表示待处理的元素
  
  ## characteristics
 表示这个Spliterator的特征:ordered,distinct,sorted,immuable,concurrent,sized,subsized, nonnull8个特征。
  
  ## default forEachRemaining
  默认方法，底层就是do { } while (tryAdvance(action))
  
  ## default getExactSizeIfKnown
  默认方法。获取sized特性的剩余遍历元素个数
  
  ## characteristics
  返回splitor特性的计算值
  
  ## default hasCharacteristics
  返回是否有某种特性
  
  ## default getComparator
  如果是排过序的返回比较器（可能为null），不是IllegalStateException异常，默认实现是一直抛异常的
  
  ## 定义在内部的接口
  Of系列
  
  
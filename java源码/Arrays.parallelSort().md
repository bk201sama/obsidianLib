# 正文
有一系列重载方法
1. `public static void parallelSort(int[] a)` 当数组的长度小于等于MIN_ARRAY_SORT_GRAN = 1 << 13 = 8192 的大小或者p = [[ForkJoinPool.getCommonPoolParallelism()]] == 1的时候，就会使用[[DualPivotQuicksort.sort()]]排序算法。否则它创建了一个ArraysParallelSortHelpers.FJInt.Sorter类进行并行排序。同样的还有long，short，char，byte，float，double。
2. `public static void parallelSort(int[] a, int fromIndex, int toIndex)` 对int数组的from到to位置排序,闭区间。排序之前会调用内部rangeCheck方法检验索引是否合法。其他与1一致。
3. `public static <T extends Comparable<? super T>> void parallelSort(T[] a)`对[[Compareble]] 的数组排序。当数组的长度小于等于MIN_ARRAY_SORT_GRAN = 1 << 13 = 8192 的大小或者p = [[ForkJoinPool.getCommonPoolParallelism()]] == 1的时候，调用Timesort.sort()。否则调用ArraysParallelSortHelpers.FJObject.Sorter（）。
4. `public static <T extends Comparable<? super T>>  
void parallelSort(T[] a, int fromIndex, int toIndex)`对[[Compareble]] 数组的from到to位置排序,闭区间。排序之前会调用内部rangeCheck方法检验索引是否合法。其他与3一致。
5. `public static <T> void parallelSort(T[] a, Comparator<? super T> cmp)`如果比较器为null，直接按照数组的方式操作。否则判断[[LegacyMergeSort.userRequested]]，如果真则调用legacyMergeSort(),否则调用TimSort.sort()。

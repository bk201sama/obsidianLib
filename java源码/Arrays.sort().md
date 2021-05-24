# 正文
有一系列重载方法
* `public static void sort(int[] a)` 对int数组排序。直接调用[[DualPivotQuicksort]](双轴快排) 的sort方法，同样的还有long，short，char，byte，float，double
* `public static void sort(int[] a, int fromIndex, int toIndex)` 对int数组的from到to位置排序,闭区间。排序之前会调用内部rangeCheck方法检验索引是否合法，然后调用[[DualPivotQuicksort]](双轴快排)。同样的还有long，short，char，byte，float，double
*  `public static void sort(Object[] a)` 对object数组排序。判断LegacyMergeSort.userRequested，如果真则调用legacyMergeSort(),否则调用ComparableTimSort.sort()。	
*  `public static <T> void sort(T[] a, Comparator<? super T> c)` 如果比较器为null，直接按照数组的方式操作。否则判断[[LegacyMergeSort.userRequested]]，如果真则调用legacyMergeSort(),否则调用TimSort.sort()。
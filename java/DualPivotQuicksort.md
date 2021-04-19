# INTRO
[[Arrays]]类中提供的给基本类型的数据排序的算法
# Structure
1.  判断数组的长度是否大于286（QUICKSORT_THRESHOLD），大于则使用归并排序[[merge sort]]，否则使用执行2
2.  判断数组长度是否小于47（INSERTION_SORT_THRESHOLD），小于则直接采用插入排序[[insertion sort]]，否则执行3
3.  使用length/8+length/64+1近似计算出数组长度的1/7（涉及到1 + x + x^2 + x^3 + ... = 1 / (1 - x)麦克劳林公式，详细参见[java - How does this approximation of division using bit shift operations work? - Stack Overflow](https://stackoverflow.com/questions/33063691/how-does-this-approximation-of-division-using-bit-shift-operations-work)）
4.  .取5个根据经验得出的等距点
5.  将这5个元素进行插入排序
6.  选取a\[e2\]，a\[e4\]分别作为pivot1，pivot2。由于步骤5进行了排序，所以必有pivot1 <= pivot2。定义两个指针less和great，less从最左边开始向右遍历，一直找到第一个不小于pivot1的元素，great从右边开始向左遍历，一直找到第一个不大于pivot2的元素。



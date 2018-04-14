# LeetCode 56

* 作者：hongdong（洪冬）
* 版本 2018-04-11

## 题目描述
> Given a collection of intervals, merge all overlapping intervals.

> For example:
Given [1,3],[2,6],[8,10],[15,18],
return [1,6],[8,10],[15,18].


## 思路报告
- 理解步骤
1. 判断长度是否少于2个，节省不必要资源开销
2. 将 start 与 end 分别取出后排序
3. 双指针扫描 start 与 end (寻找开始点大于结束点的情况)
4. 找到后记录查找最初的情况start[j]点 end[i]点，再将j点位置跟进到i+1(下一个起始点)
5. 依次遍历比较直到结束（注意 i+1位置的越界问题）

- 思路理解
1. 另一个解法在于记录上一次节点信息，将当前start & end 与 上一次节点的 end进行比较，并更新缓存的上一次节点信息

- 遇到问题
1. 下标越界问题需要注意
2. 前后边界问题,相关动态指针值修改
3. 手写Arrays.sort(xx)。(非Array)

#### JAVA代码
```java
/**
 * Definition for an interval.
 * public class Interval {
 *     int start;
 *     int end;
 *     Interval() { start = 0; end = 0; }
 *     Interval(int s, int e) { start = s; end = e; }
 * }
 */
class Solution {
    public List<Interval> merge(List<Interval> intervals) {
        int size = intervals.size();
        if(size <= 1) return intervals;
        
        int[] start = new int[size];
        int[] end = new int[size];
        for(int i = 0; i < size; i++){
            start[i] = intervals.get(i).start;
            end[i] = intervals.get(i).end;
        }
        
        Arrays.sort(start);
        Arrays.sort(end);
        
        List<Interval> nsl = new ArrayList();
        for(int i = 0, j = 0; i< size; i++){
            if(i == size-1 || start[i+1]> end[i]){
                nsl.add(new Interval(start[j], end[i]));
                j = i+1;
            }
        }
        return nsl;
    }
}


```


## 套路总结
- 比较类型的问题可转化为 指针类型的问题解决
- 区间比较问题，优先考虑排序后结果进行思考

# LeetCode 277 Find the Celebrity

* 作者：hongdong（洪冬）
* 版本 2018-04-12

## 题目描述 Problem:

>Suppose you are at a party with n people (labeled from 0 to n - 1) and among them, there may exist one celebrity. The definition of a celebrity is that all the other n - 1people know him/her but he/she does not know any of them.

>Now you want to find out who the celebrity is or verify that there is not one. The only thing you are allowed to do is to ask questions like: "Hi, A. Do you know B?" to get information of whether A knows B. You need to find out the celebrity (or verify there is not one) by asking as few questions as possible (in the asymptotic sense).

>You are given a helper function bool knows(a, b) which tells you whether A knows B. Implement a function int findCelebrity(n), your function should minimize the number of calls to knows.

___ Note:___  There will be exactly one celebrity if he/she is in the party. Return the celebrity's label if there is a celebrity in the party. If there is no celebrity, return -1.


## 思路报告
- 理解步骤
1. celebrity 不认识任何人，但是(n-1)个都认识他，可能有一个celebrity也可能没有；用最少的询问knows(a, b)找出celebrity 或不存在；
2. 我们可以假设随机一个人是celebrity，通过遍历检查knows(a, b)是否有人不认识我们当前假设的celebrity 全部认识返回该celebrity，如果有人不认识，切换到下一个假设，继续验证 此复杂度为O(n^2)
3. 优化根据 celebrity 谁都认识他的特性 一次遍历缩小将假设范围（结果只可能为是celebrity，不是celebrity）
4. 再次遍历 检查第一次假设得到的 celebrity 全部不认识或认识别人即可得 -1 否者 celebrity

- 遇到问题
1. 首先想到的是双指针问题，可求解，但复杂度太高
2. 不清楚一个值如何判断是否为名人；

- 复杂度
- 时间：O(n)

#### JAVA代码
```java

public class Solution extends Relation {
    public int findCelebrity(int n) {
        if(n < 2) throw new IllegalArgumentException("无效参数");
        int celeb = 0;
        for(int i =0; i < n; ++i){ //假设0为 celebrity 
            if(knows(i,celeb)){
                celeb = celeb;
            }else {
                celeb = i;
            }
        }
        int e = 0;
        while(e < n){
            if(caleb!=e && (knows(e,celeb)||!knows(eleb,e))){
                return caleb;
            }
            e++；
        }
        return -1;
    }
}

```


## 套路总结
- 两步走，简化算法问题复杂度
- 算是简单的备忘录模型，

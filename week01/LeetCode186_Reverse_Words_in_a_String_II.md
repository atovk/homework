# LeetCode 186 Reverse Words in a String II

* 作者：hongdong（洪冬）
* 版本 2018-04-11

## 题目描述
> Given an input string, reverse the string word by word. A word is defined as a sequence of non-space characters.

> The input string does not contain leading or trailing spaces and the words are always separated by a single space.

> For example,
Given s = "the sky is blue",
return "blue is sky the".
Could you do it in-place without allocating extra space?


## 思路报告
- 理解步骤
1. in-place条件下，先将每个词内的字母先反转过来，
2. 再将整个 反转过来 

- 遇到问题
1. 前后交换逻辑容易边界混淆
2. 指针的位置移动容易混淆

#### JAVA代码 
```java
public class Solution {  

    public void reverseWords(char[] s) {  
        int pos = 0;  
        for(int i=0; i<=s.length; i++) {  
            if (i<s.length && s[i] != ' ') continue;  
            reverse(s, pos, i-1);  
            pos = i+1;  
        }  
        reverse(s, 0, s.length-1);  
    }  
    private void reverse(char[] s, int start, int end) {  
        while (start < end) {  
            char c = s[start];  
            s[start] = s[end];  
            s[end] = c;  
            start ++;  
            end --;  
        }  
    }  
}  


```


## 套路总结
- 双针模型
- 涉及反转的大部分与双针有关系

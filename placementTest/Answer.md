#Section I
##1. Given the following code snippet, what will be the output of method “getResult” ?
- str1:  Tigger
- str2:  Bit
- str1:  Bittiger

##2. What’s the Time & Space Complexity for quick sort and mergesort (BigO notation)?
- quick sort:
	- Time：
		（不稳定）平均情况是：O(nlog(n)) 最坏的情况是 n^2 的复杂度。
	- Space：
		O(n)

- merge sort：
	- Time：
		O(nlog(n))
	- Space：
		O(n)

##3. Assuming we are calculating the value of nth element of a Fibonacci Array: 1, 1, 2, 3, 5, 8, 13, 21...... Please indicate what will happen if you run the following code and modify it if you believe it is incorrect.

```java

public int fibonacci (int n) {

	if(n < 0) throw new IllegalArgumentException("Illegal Argument n");

	return n < 2 ? 1 : fibonacci(n - 1) + fibonacci(n - 2);

}

```

##4. The computational complexity for adding(list.add()) one element to an Java ArrayList is _______ ? 	

ArrayList 为无间隙数据结构，插入删除大多数情况下都需要更新下标，检索（定位）和修改不需要，则：插入O(N),删除O(N),检索（定位）O(1),修改O(1);

##5. Please differentiate data strucuture: Stack, Queue and Deque in shortest words. 

- Stack：FILO  
- Queue：FIFO 
- Deque： AIAO(FILO + FIFO); --!

##6. What’s the value of maximum integer and minimum integer in JAVA(in 2^n format)
 
__Max:_2^(31)_+ (-1)___; __Min:_-2^(31)_+_(0)_

##7. What’s a correct and efficient way you believe to initialize an integer Stack/Queue/ArrayList in JAVA? Please write the three complete lines here, each for one data structure declaration correspondingly.
```java

 // Stack
    Stack stack = new Stack();
 // Queue
    Queue queue = new Queue();
 //ArrayList
    List arrayList = new ArrayList();
    
```

##8. Given the following code snippet, what will be the output of method “getResult” ?
// java 默认创建在 同一个 string 对象中 所以引用相等，不同对象比较需要使用 equals
- true
- false
- false

###Section II
> 1. Given two non-negative integers num1 and num2 represented as string, return the sum of num1 and num2.
Note:
The length of both num1 and num2 is < 5100.
Both num1 and num2 contains only digits 0-9.
Both num1 and num2 does not contain any leading zero.
You must not use any built-in BigInteger library or convert the inputs to integer directly.

```java

public class Solution{
    
	    public String addStrings(String num1, String num2){
        // 不考虑负数
        if(num1 == null || num2 == null) throw new IllegalArgumentException("Illegal Argument : has null！");
        int adding = 0;
        int len1 = num1.length()-1;
        int len2 = num2.length()-1;
        StringBuffer strBuff = new StringBuffer();

        while(len1>-1 || len2>-1){
            int sumValue = (len1>-1? num1.charAt(len1--)-'0':0) + (len2>-1? num2.charAt(len2--)-'0':0) + adding;
            adding = sumValue<10? 0:1;

            strBuff.insert(0,sumValue%10);
        }
        return strBuff.toString();
    }
}

```

>2. Invert a binary tree.
>    4
   /   \
  2     7
 / \   / \
1   3 6   9
to
>    4
   /   \
  7     2
 / \   / \
9   6 3   1
Trivia:
This problem was inspired by this original tweet by Max Howell:
Google: 90% of our engineers use the software you wrote (Homebrew), but you can’t invert a binary tree on a whiteboard so fuck off.

```java
public class Solution{
    public TreeNode invertTree(TreeNode root){
        if(root==null) return root; // 可提价判断无叶子节点情况
        TreeNode temp = root.right;
        root.left = invertTree(root.right);
        root.fight = invertTree(root.left);
        return root;
    }
}


```

>Find the kth largest element in an unsorted array. Note that it is the kth largest element in the sorted order, not the kth distinct element.
For example,
Given [3,2,1,5,6,4] and k = 2, return 5.
Note:
You may assume k is always valid, 1 <=  k <=  array's length.

```java

public class Solution {
    public int findKthLargest(int[] nums, int k) {

    }
}


```

>You are given coins of different denominations and a total amount of money amount. Write a function to compute the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.
Example 1:
coins = [1, 2, 5], amount = 11
return 3 (11 = 5 + 5 + 1)
Example 2:
coins = [2], amount = 3
return -1.
Note:
You may assume that you have an infinite number of each kind of coin. 

```java

public class Solution {
    public int coinChange(int[] coins, int amount) {
                
    }
}

```



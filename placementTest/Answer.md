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
Public class Solution{
    int adding = 0;
	Public String addStrings(String num1, String num2){
        
    }
}

```
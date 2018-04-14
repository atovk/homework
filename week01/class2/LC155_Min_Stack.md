# LeetCode 155 Min Stack

* 作者：hongdong（洪冬）
* 版本 2018-04-12

## 题目描述
>Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

- push(x) -- Push element x onto stack.
- pop() -- Removes the element on top of the stack.
- top() -- Get the top element.
- getMin() -- Retrieve the minimum element in the stack.

```text
Example:
MinStack minStack = new MinStack();
minStack.push(-2);
minStack.push(0);
minStack.push(-3);
minStack.getMin();   --> Returns -3.
minStack.pop();
minStack.top();      --> Returns 0.
minStack.getMin();   --> Returns -2.
```
Follow up: 怎么节省最小栈中的存储

## 思路报告
- 理解步骤
1. 最小栈问题 可以多置入一个栈存储当前最小值信息
2. push 时比较当前值是否小于最小栈中的值，小于加入else将最小栈中的值再存储一遍
3. pop 将stack中的pop值与minStack.peek 值进行比较，等于将 minStack.pop出
4. top peek当前stack顶端的值
5. getMin 获取最小栈栈顶端的值

- 遇到问题
1. API 不属虚（自己写了三遍）
2. 边界条件问题处理 开始不容易整理清楚
3. 还有其它 fllow up （单STACK，相同元素存储优化）
4. 写完代码记得 rewiew，细节大意问题

- 算法复杂度
时间：O(1)
空间：O(n)

#### JAVA代码
```java

class MinStack {
    private Deque<Integer> stk = null;
    private Deque<Integer> minstk = null;
    /** initialize your data structure here. */
    public MinStack() {
        stk = new ArrayDeque();
        minstk = new ArrayDeque();
    }
    
    public void push(int x) {
        stk.push(x);
        if(minstk.isEmpty() || x <= minstk.peek()){
            minstk.push(x);
        }
    }
    
    public void pop() {
        if(!minstk.isEmpty() && stk.pop().equals(minstk.peek())){
            minstk.pop();
        }
    }
    
    public int top() {
        return stk.peek();
    }
    
    public int getMin() {
        return minstk.peek();
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(x);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */

```


## 套路总结
- 设计题需要考虑 相关类的初始化及内部参数的安全访问及相关数据类型在语言中的最优适用原则
- 

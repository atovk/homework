<<<<<<< HEAD:week01/class1/LeetCode234_Palindrome_Linked_List.md
# LeetCode 234
=======
# LeetCode 234. Palindrome Linked List
>>>>>>> 87777de0d451c81926227968dff624fabdfc2574:week01/LeetCode234_Palindrome_Linked_List.md

* 作者：hongdong（洪冬）
* 版本 2018-04-11

## 题目描述
> Given a singly linked list, determine if it is a palindrome.

> Follow up:
Could you do it in O(n) time and O(1) space?

## 思路报告
- 理解步骤
1. 判断是否为 palindrome 需要 arraylist中可以头尾双指针扫描对比
2. 但是单链表的特性在不记录的情况下遍历时无法得知父节点信息
3. palindrome 必然是前后(n/2)或(n-1)/2 长度对称
4. 在O(1)空间的情况下 可以将中点以后的节点反转过来
5. 将原始链表的头部与反转链表的头部同时向下比较
注意：
1. 链表存在奇偶性，所以快慢指正需要判断是否为空，决定慢节点是否需要向下移动一位；


- 遇到问题
1. 快慢指正 初次使用不好理解，演算正确 但是想不通为什么（模式化的记住了指正倍数）


#### JAVA代码 （此参考 leetcode 代码）
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public boolean isPalindrome(ListNode head) {
        ListNode fast = head;
        ListNode slow = head;

        while(fast != null && fast.next != null) {
            fast = fast.next.next;
            slow = slow.next;
        }
        if(fast != null) slow = slow.next;
    
        slow = reverse(slow);
        while(slow != null && head.val == slow.val) {
            head = head.next;
            slow = slow.next;
        }
        return slow == null;
    }

    private ListNode reverse(ListNode head) {
        ListNode prev = null;
        while(head != null) {
            ListNode next = head.next;
            head.next = prev;
            prev = head;
            head = next;
        }
        return prev;
    }
}


```


## 套路总结
- 链表检查问题很对可以用快慢指针解决，（检查环形链表，检查回文）
- 配合基础的 链表翻转
- 快慢指针倍数 
- 双针模型

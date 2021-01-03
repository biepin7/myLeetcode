# [链表] [双指针] leetcode 86 分割链表

## 题目

给你一个链表和一个特定值 x ，请你对链表进行分隔，使得所有小于 x 的节点都出现在大于或等于 x 的节点之前。

你应当保留两个分区中每个节点的初始相对位置。

Given a linked list and a value x, partition it such that all nodes less than x come before nodes greater than or equal to x.

You should preserve the original relative order of the nodes in each of the two partitions.

> ```
> Input: head = 1->4->3->2->5->2, x = 3
> Output: 1->2->2->4->3->5
> ```

## 思路

非常明显的双指针，维护两个链表：

- `small`:顺序存储所有小于`x`的节点
- `big`：顺序存储所有大于`x`的节点

遍历整个`head`，向`samll`和`big`中分配节点，最后合并两个链表并返回

## 细节

设定

```
ListNode* small_head = small;
ListNode* big_head = big;
```

来方便遍历

结束遍历后，需要：

```
small->next=big_head->next;
big->next=nullptr;
```

## C++

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* partition(ListNode* head, int x) {
        //新建两个列表
        ListNode* small = new ListNode(0);
        ListNode* big = new ListNode(0);
        //两个新列表的头
        ListNode* small_head = small;
        ListNode* big_head = big;
        //遍历head
        while(head!=nullptr)
        {
            if(head->val < x)
            {
                // 把当前的节点，append到small，small
                small = small->next = head;
            }
            else{
                // 把当前的节点，append到big，更新big
                big =big->next = head;
            }
            head=head->next;
        }
        small->next=big_head->next;
        big->next=nullptr;
        return small_head->next;
    }
};
```
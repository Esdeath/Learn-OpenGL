#LeetCode总结

##链表
1.单链表反转

地址:https://leetcode.com/problems/reverse-linked-list/

题解1:

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */

struct ListNode* reverseList(struct ListNode* head) {

    if(!head || !head->next) return head;
     struct ListNode* p = head;
     struct ListNode* q = head->next;
     struct ListNode* r = NULL;
     
     while(q != NULL){
         p->next = r;
         r = p;
         p = q;
         q = q->next;
     }
     p->next = r;
     return p;
}

```
题解2:

```
struct ListNode* reverseList(struct ListNode* head) {
    struct ListNode* middle;
    struct ListNode* foot;
    middle = NULL;
    
    while(head){
        foot = middle;
        middle = head;
        head = head->next;
        middle->next = foot;
    }
    
    return middle;
}
```
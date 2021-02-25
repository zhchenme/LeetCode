```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        Set<ListNode> nodeList = new LinkedHashSet<>();
        ListNode aNextNode = headA;
        while (aNextNode != null) {
            nodeList.add(aNextNode);
            aNextNode = aNextNode.next;
        }
        ListNode bNextNode = headB;
        while (bNextNode != null) {
            if (nodeList.contains(bNextNode)) {
                return bNextNode;
            }
            bNextNode = bNextNode.next;
        }
        return null;
    }
}
```

```java
public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        ListNode aNode = headA;
        ListNode bNode = headB;
        while (aNode != bNode) {
            aNode = aNode != null ? aNode.next : headB;
            bNode = bNode != null ? bNode.next : headA;
        }
        return aNode;
    }
}
```
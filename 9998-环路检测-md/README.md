```java
/**
 * Definition for singly-linked list.
 * class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */
public class Solution {
    public ListNode detectCycle(ListNode head) {
        Set<ListNode> nodeSet = new HashSet<>();
        nodeSet.add(head);
        while (head != null) {
            if (nodeSet.contains(head.next)) {
                return head.next;
            }
            nodeSet.add(head.next);
            head = head.next;
        }
        return null;
    }
}
```

```java

```
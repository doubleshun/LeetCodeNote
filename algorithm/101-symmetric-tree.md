# \#101 Symmetric Tree

Given a binary tree, check whether it is a mirror of itself \(ie, symmetric around its center\).

For example, this binary tree `[1,2,2,3,4,4,3]` is symmetric

```text
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isSymmetric(self, root: TreeNode) -> bool:
        if root == None :
            return True
        elif root.left == None and root.right != None:
            return False
        elif root.left != None and root.right == None:
            return False
        elif root.left == None and root.right == None:
            return True
        else :
            p = root.left
            q = root.right
            if p.val == q.val :
                return isSameTree(p.left,q.right) and isSameTree(p.right,q.left)
            
def isSameTree(p: TreeNode, q: TreeNode) -> bool:
    if p == None and q == None :
        return True
    elif p == None and q != None :
        return False
    elif p != None and q == None:
        return False
    elif p.val == q.val :
        return isSameTree(p.left,q.right) and isSameTree(p.right,q.left)
    else:
        return False
```


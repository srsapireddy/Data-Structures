# Data-Structures-and-Algorithms

## Arrays
![image](https://github.com/srsapireddy/Data-Structures-and-Algorithms/assets/32967087/450042f5-3cd2-4870-bb91-94118053579c)
## Dictionaries
![image](https://github.com/srsapireddy/Data-Structures-and-Algorithms/assets/32967087/a6ab8c5a-82d7-45c6-8801-e00e9fa4ec04)
## Singly Linked Lists
![image](https://github.com/srsapireddy/Data-Structures-and-Algorithms/assets/32967087/87e9c9b4-6c7a-402d-b02e-d28e59b1bad4)
## Doubly Linked Lists: Require More memory due to additional pointers
![image](https://github.com/srsapireddy/Data-Structures-and-Algorithms/assets/32967087/d035836e-7bd5-43ab-a6b1-7e14b2eb6e11)

## Reference
[1] https://docs.python.org/3/library/collections.html#collections.deque </br>
[2] https://leetcode.com/discuss/general-discussion/1152824/cracking-the-coding-interview-6th-edition-in-leetcode </br>
[3] https://leetcode.com/list/5kiae7i1/ </br>
[4] https://github.com/jwasham/coding-interview-university?tab=readme-ov-file#sorting </br>

## BST
```
from types import new_class
class Node:
  def __init__(self,value):
    self.value = value
    self.left = None
    self.right = None

class BinarySearchTree:
  def __init__(self):
    self.root = None

  def insert(self,value):
    new_node = Node(value)
    if not self.root:
      self.root = new_node
      return self
    current_node = self.root
    while value != current_node.value:
      if value < current_node.value:  
        if not current_node.left:
          current_node.left = new_node
          break
          current_node = current_node.left
      else:
        if not current_node.right:
          current_node.right = new_node
          break
          current_node = current_node.right
    return self   

  def contains(self,value):
    current_node = self.root
    while current_node:
        if value == current_node.value:
          return True
        if value < current_node.left
          current_node = current_node.left
        else:
          current_node = current_node.right
    return False

  def remove(self, value, start: None, parent: None):
    current = start or self.root
    while current and current.value != value:
      parent = current
      if value < current.value:
        current = parent.left
      else:
        current = parent.right
    if not current:
      raise Exception("item not in tree")
    # To check if the current node is the leaf and verifiying that both the right and left children dont exist
    if not current.right and not current.left:
      return self._remove_node_no_children(current, parent)
    if current.right and current.left:
      return self._remove_node_tow_children(current)
    return self._remove_node_one_child(current,parent)



my_tree = BinarySearchTree()
my_tree.insert(20)
my_tree.insert(19)
my_tree.insert(21)
print(my_tree.root.value)

## Insert Method:
# Time complexity: O(1) The variable reassignment we do inside the while loop dosse not consume more memory. We are just updating the same one over and over again so we dont keep the old values.
# Space complexity: 
### Best: O(logn) For a perfectly balanced tree. Here with one comparison for the new node with the root we can exclude the half of the values of the tree. And the same thing happens for the sub-trees. 
### Worst: O(n) Example: Tree structure like a stick 

## Contains Method:
# Time complexity: 
## Best: O(logn)
## Worst: 0(n)
# Space complexity: O(1)
```

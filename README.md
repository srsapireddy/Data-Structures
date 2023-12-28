# Data-Structures-and-Algorithms

## Arrays
![image](https://github.com/srsapireddy/Data-Structures-and-Algorithms/assets/32967087/450042f5-3cd2-4870-bb91-94118053579c)
## Dictionaries
![image](https://github.com/srsapireddy/Data-Structures-and-Algorithms/assets/32967087/a6ab8c5a-82d7-45c6-8801-e00e9fa4ec04)
## Singly Linked Lists
```
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class SinglyLinkedList:
    def __init__(self): # self is a reference to the instance being created
        self.head = None
        self.tail = None
        self._length = 0
    # Append to Lists
    def append(self, value):
        new_node = Node(value) 
        if not self._length:
            self.head = self.tail = new_node
        else:
            self.tail.next = new_node
            self.tail = new_node
        self._length += 1
        return self

    # Prepend to list
    def prepend(self, value):
        new_node = Node(value)
        if not self._length:
            self.head = self.tail = new_node
        else:
            new_node.next = self.head
            self.head = new_node
        self._length += 1
        return self

    def pop_left(self):
        if not self._length:
            raise Exception("list is empty")
        former_head = self.head
        self.head = former_head.next
        former_head.next = None
        self._length -= 1
        if not self._length:
            self.tail = None
        return former_head.value

    def pop_right(self):
        if not self._length:
            raise Exception("list is empty")
        tail_value = self.tail.value
        if self._length == 1:
            self.head = self.tail = None
        else:
            temp_node = self.head
            while temp_node.next is not self.tail:
              temp_node = temp_node.next
            self.tail = temp_node
            self.tail.next = None
        self._length -= 1
        return tail_value

my_list = SinglyLinkedList()
my_list.append(3)
my_list.append(5)
my_list.append(8)
my_list.prepend(14)
my_list.pop_left()
my_list.pop_right()

print(my_list)
print(my_list.head.value)
print(my_list.tail.value)
print(my_list._length)

## Append Method:
# Time complexity: O(1)
# Space complexity: Does our function adds more things to memory? Yes. We create a new node with every function call. O(1)

## Prepend Method:
# Time complexity: O(1)
# Space complexity: O(1)

## Pop Left Method:
# Time complexity: O(1)
# Space complexity: O(1)

## Pop Right Method:
# Time complexity: Running time of the function depend on the size of the list due to the while loop. O(n)
# Space complexity: O(1)
```

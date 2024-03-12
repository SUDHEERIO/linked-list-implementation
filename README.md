# linked-list-implementation
Question: Reversing a Linked List Implementation ?
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_beginning(self, value):
        new_node = Node(value)
        new_node.next = self.head
        self.head = new_node

    def reverse(self):
        prev = None
        current = self.head
        while current:
            next_node = current.next
            current.next = prev
            prev = current
            current = next_node
        self.head = prev

    def get_linked_list(self):
        result = []
        current = self.head
        while current:
            result.append(current.value)
            current = current.next
        return result

# Function to take user input for creating linked list
def create_linked_list():
    linked_list = LinkedList()
    n = int(input("Enter the number of elements in the linked list: "))
    for _ in range(n):
        value = int(input("Enter element value: "))
        linked_list.insert_at_beginning(value)
    return linked_list

# Test Case
linked_list1 = create_linked_list()
print("Original Linked List:", linked_list1.get_linked_list())
linked_list1.reverse()
print("Reversed Linked List:", linked_list1.get_linked_list())

2).Question: Linked List Implementation with Deletion at Middle ?
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_end(self, value):
        new_node = Node(value)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

    def delete_at_middle(self):
        if not self.head:
            return
        slow = fast = self.head
        prev = None
        while fast and fast.next:
            fast = fast.next.next
            prev = slow
            slow = slow.next
        if prev:
            prev.next = slow.next
        else:
            self.head = slow.next

    def display(self):
        result = []
        current = self.head
        while current:
            result.append(current.value)
            current = current.next
        print(result)

# Function to take user input for creating linked list
def create_linked_list():
    linked_list = LinkedList()
    n = int(input("Enter the number of elements in the linked list: "))
    for _ in range(n):
        value = int(input("Enter element value: "))
        linked_list.insert_at_end(value)
    return linked_list

# Test Case
ll1 = create_linked_list()
ll1.display()
ll1.delete_at_middle()
ll1.display()

3).Question: Linked List Implementation with Displaying Middle Element ?
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_end(self, value):
        new_node = Node(value)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

    def display_middle_element(self):
        if not self.head:
            print("The linked list is empty.")
            return

        slow = fast = self.head

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

        print(f"The middle element of the linked list is {slow.value}")

# Function to take user input for creating linked list
def create_linked_list():
    linked_list = LinkedList()
    n = int(input("Enter the number of elements in the linked list: "))
    for _ in range(n):
        value = int(input("Enter element value: "))
        linked_list.insert_at_end(value)
    return linked_list

# Test Case
ll1 = create_linked_list()
ll1.display_middle_element()

4).4).Question: Reversing a Portion of a Linked List ?
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_end(self, value):
        new_node = Node(value)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

    def reverse_in_range(self, start, end):
        if start == end or not self.head:
            # No range to reverse or empty linked list
            return

        dummy = Node(0)
        dummy.next = self.head
        prev = dummy

        for _ in range(start - 1):
            prev = prev.next

        current = prev.next
        next_node = None

        for _ in range(end - start + 1):
            temp = current.next
            current.next = next_node
            next_node = current
            current = temp

        prev.next.next = current
        prev.next = next_node

        self.head = dummy.next

    def display(self):
        result = []
        current = self.head
        while current:
            result.append(current.value)
            current = current.next
        print(result)

# Function to take user input for creating linked list and specifying the range
def create_linked_list():
    linked_list = LinkedList()
    n = int(input("Enter the number of elements in the linked list: "))
    for _ in range(n):
        value = int(input("Enter element value: "))
        linked_list.insert_at_end(value)
    return linked_list

# Test Case
ll1 = create_linked_list()
ll1.display()

start_range = int(input("Enter the starting index to reverse: "))
end_range = int(input("Enter the ending index to reverse: "))
ll1.reverse_in_range(start_range, end_range)

ll1.display()

1)Question: Reversing a Linked List Implementation ?
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None
class LinkedList:
    def __init__(self):
        self.head = None
    def insert_at_beginning(self, value):
        new_node = Node(value)
        new_node.next = self.head
        self.head = new_node
    def reverse(self):
        prev = None
        current = self.head
        while current:
            next_node = current.next
            current.next = prev
            prev = current
            current = next_node
        self.head = prev
    def get_linked_list(self):
        result = []
        current = self.head
        while current:
            result.append(current.value)
            current = current.next
        return result

# Test Case 1
linked_list1 = LinkedList()
linked_list1.insert_at_beginning(5)
linked_list1.reverse()
print(linked_list1.get_linked_list())  # Output: [5]
2) Question: Linked List Implementation with Deletion at Middle ?
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None
class LinkedList:
    def __init__(self):
        self.head = None
    def insert_at_end(self, value):
        new_node = Node(value)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node
    def delete_at_middle(self):
        if not self.head:
            return
        slow = fast = self.head
        prev = None
        while fast and fast.next:
            fast = fast.next.next
            prev = slow
            slow = slow.next
        if prev:
            prev.next = slow.next
        else:
            self.head = slow.next
    def display(self):
        result = []
        current = self.head
        while current:
            result.append(current.value)
            current = current.next
        print(result)
# Test Case 1
ll1 = LinkedList()
ll1.insert_at_end(3)
ll1.insert_at_end(7)
ll1.insert_at_end(11)
ll1.delete_at_middle()
ll1.display()

3)Question: Linked List Implementation with Displaying Middle Element ?
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_end(self, value):
        new_node = Node(value)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

    def display_middle_element(self):
        if not self.head:
            print("The linked list is empty.")
            return

        slow = fast = self.head

        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

        print(f"The middle element of the linked list is {slow.value}")

# Test Case 1
ll1 = LinkedList()
ll1.insert_at_end(3)
ll1.insert_at_end(7)
ll1.insert_at_end(11)
ll1.display_middle_element()

4))Question: Reversing a Portion of a Linked List ?
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_end(self, value):
        new_node = Node(value)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

    def reverse_in_range(self, start, end):
        if start == end or not self.head:
            # No range to reverse or empty linked list
            return

        dummy = Node(0)
        dummy.next = self.head
        prev = dummy

        for _ in range(start - 1):
            prev = prev.next

        current = prev.next
        next_node = None

        for _ in range(end - start + 1):
            temp = current.next
            current.next = next_node
            next_node = current
            current = temp

        prev.next.next = current
        prev.next = next_node

        self.head = dummy.next

    def display(self):
        result = []
        current = self.head
        while current:
            result.append(current.value)
            current = current.next
        print(result)

# Test Case 1
ll1 = LinkedList()
ll1.insert_at_end(1)
ll1.insert_at_end(2)
ll1.insert_at_end(3)
ll1.insert_at_end(4)
ll1.reverse_in_range(2, 3)
ll1.display()

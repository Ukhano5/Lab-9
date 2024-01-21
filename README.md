# Lab-9
Muhammad Umair 
12370
Se 3rdC

 Q1: Write a function to check if a binary tree is a BST using only traversals.
def is_bst_using_traversals(root, prev=[float('-inf')]):
    if root is None:
        return True

    if not is_bst_using_traversals(root.left, prev):
        return False

    if root.key <= prev[0]:
        return False

    prev[0] = root.key

    return is_bst_using_traversals(root.right, prev)

Output for Q1: No direct output, as it is a function definition.

 Q2: Implement a function to convert a sorted array into a balanced BST.
def sorted_array_to_bst(arr):
    if not arr:
        return None

    mid = len(arr) // 2
    root = Node(arr[mid])

    root.left = sorted_array_to_bst(arr[:mid])
    root.right = sorted_array_to_bst(arr[mid+1:])

    return root

 Output for Q2: No direct output, as it is a function definition.

# Q3: Implement a function to create a complete binary tree from a given array.
def array_to_complete_binary_tree(arr):
    if not arr:
        return None

    nodes = [Node(value) for value in arr]
    for i in range(len(nodes) // 2):
        if nodes[i]:
            nodes[i].left = nodes[2*i + 1] if 2*i + 1 < len(nodes) else None
            nodes[i].right = nodes[2*i + 2] if 2*i + 2 < len(nodes) else None

    return nodes[0]

 Output for Q3: No direct output, as it is a function definition.

 Q4: Write a function to perform a level order traversal of a binary tree.
def level_order_traversal(root):
    result = []
    if root is None:
        return result

    queue = [root]
    while queue:
        current = queue.pop(0)
        result.append(current.key)
        if current.left:
            queue.append(current.left)
        if current.right:
            queue.append(current.right)

    return result

 Output for Q4: No direct output, as it is a function definition.

# Q5: Create a function to construct an expression tree from a given postfix expression.
def construct_expression_tree(postfix):
    stack = []

    for char in postfix:
        if char.isalnum():
            stack.append(Node(char))
        else:
            right = stack.pop()
            left = stack.pop()
            stack.append(Node(char, left, right))

    return stack[0] if stack else None

 Output for Q5: No direct output, as it is a function definition.
```

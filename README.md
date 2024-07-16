# EstruturaDeDados
Framework de estrutura de dados
---
Bom dia! Vou te ajudar com um tutorial sobre pilhas, filas e outras estruturas de dados básicas em Python. Vou explicar cada uma delas com exemplos de código comentados. No final, vou fornecer a documentação em Markdown que você pode usar.

## Pilhas (Stacks)

### O que é uma Pilha?

Uma pilha é uma estrutura de dados linear que segue o princípio LIFO (Last In, First Out), ou seja, o último elemento a ser inserido é o primeiro a ser removido.

### Operações Básicas

- **push**: Adiciona um elemento no topo da pilha.
- **pop**: Remove o elemento do topo da pilha.
- **peek**: Retorna o elemento do topo sem removê-lo.
- **is_empty**: Verifica se a pilha está vazia.

### Exemplo de Código em Python

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)
        print(f"Pushed: {item}")

    def pop(self):
        if not self.is_empty():
            popped_item = self.items.pop()
            print(f"Popped: {popped_item}")
            return popped_item
        else:
            print("Stack is empty")

    def peek(self):
        if not self.is_empty():
            return self.items[-1]
        else:
            return "Stack is empty"

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

# Exemplo de uso
stack = Stack()
stack.push(1)
stack.push(2)
stack.push(3)
print(stack.pop())  # Output: 3
print(stack.peek()) # Output: 2
print(stack.is_empty()) # Output: False
print(stack.size()) # Output: 2
```

## Filas (Queues)

### O que é uma Fila?

Uma fila é uma estrutura de dados linear que segue o princípio FIFO (First In, First Out), ou seja, o primeiro elemento a ser inserido é o primeiro a ser removido.

### Operações Básicas

- **enqueue**: Adiciona um elemento no final da fila.
- **dequeue**: Remove o elemento do início da fila.
- **front**: Retorna o elemento do início da fila sem removê-lo.
- **is_empty**: Verifica se a fila está vazia.

### Exemplo de Código em Python

```python
class Queue:
    def __init__(self):
        self.items = []

    def enqueue(self, item):
        self.items.append(item)
        print(f"Enqueued: {item}")

    def dequeue(self):
        if not self.is_empty():
            dequeued_item = self.items.pop(0)
            print(f"Dequeued: {dequeued_item}")
            return dequeued_item
        else:
            print("Queue is empty")

    def front(self):
        if not self.is_empty():
            return self.items[0]
        else:
            return "Queue is empty"

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

# Exemplo de uso
queue = Queue()
queue.enqueue(1)
queue.enqueue(2)
queue.enqueue(3)
print(queue.dequeue())  # Output: 1
print(queue.front())    # Output: 2
print(queue.is_empty()) # Output: False
print(queue.size())     # Output: 2
```

## Listas Ligadas (Linked Lists)

### O que é uma Lista Ligada?

Uma lista ligada é uma coleção de nós onde cada nó contém um valor e um ponteiro para o próximo nó na lista.

### Operações Básicas

- **append**: Adiciona um nó ao final da lista.
- **prepend**: Adiciona um nó ao início da lista.
- **delete_with_value**: Remove o primeiro nó que contém o valor especificado.

### Exemplo de Código em Python

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
            print(f"Appended {data} as head")
            return
        last_node = self.head
        while last_node.next:
            last_node = last_node.next
        last_node.next = new_node
        print(f"Appended {data}")

    def prepend(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node
        print(f"Prepended {data}")

    def delete_with_value(self, data):
        if self.head is None:
            print("List is empty")
            return
        if self.head.data == data:
            self.head = self.head.next
            print(f"Deleted head with value {data}")
            return
        current_node = self.head
        while current_node.next and current_node.next.data != data:
            current_node = current_node.next
        if current_node.next is None:
            print(f"Value {data} not found in list")
            return
        current_node.next = current_node.next.next
        print(f"Deleted node with value {data}")

    def print_list(self):
        current_node = self.head
        while current_node:
            print(current_node.data)
            current_node = current_node.next

# Exemplo de uso
ll = LinkedList()
ll.append(1)
ll.append(2)
ll.append(3)
ll.prepend(0)
ll.print_list()
ll.delete_with_value(2)
ll.print_list()
```

## Documentação em Markdown

```markdown
# Estruturas de Dados Básicas em Python

## Pilhas (Stacks)

### O que é uma Pilha?

Uma pilha é uma estrutura de dados linear que segue o princípio LIFO (Last In, First Out), ou seja, o último elemento a ser inserido é o primeiro a ser removido.

### Operações Básicas

- **push**: Adiciona um elemento no topo da pilha.
- **pop**: Remove o elemento do topo da pilha.
- **peek**: Retorna o elemento do topo sem removê-lo.
- **is_empty**: Verifica se a pilha está vazia.

### Exemplo de Código em Python

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)
        print(f"Pushed: {item}")

    def pop(self):
        if not self.is_empty():
            popped_item = self.items.pop()
            print(f"Popped: {popped_item}")
            return popped_item
        else:
            print("Stack is empty")

    def peek(self):
        if not self.is_empty():
            return self.items[-1]
        else:
            return "Stack is empty"

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

# Exemplo de uso
stack = Stack()
stack.push(1)
stack.push(2)
stack.push(3)
print(stack.pop())  # Output: 3
print(stack.peek()) # Output: 2
print(stack.is_empty()) # Output: False
print(stack.size()) # Output: 2
```

## Filas (Queues)

### O que é uma Fila?

Uma fila é uma estrutura de dados linear que segue o princípio FIFO (First In, First Out), ou seja, o primeiro elemento a ser inserido é o primeiro a ser removido.

### Operações Básicas

- **enqueue**: Adiciona um elemento no final da fila.
- **dequeue**: Remove o elemento do início da fila.
- **front**: Retorna o elemento do início da fila sem removê-lo.
- **is_empty**: Verifica se a fila está vazia.

### Exemplo de Código em Python

```python
class Queue:
    def __init__(self):
        self.items = []

    def enqueue(self, item):
        self.items.append(item)
        print(f"Enqueued: {item}")

    def dequeue(self):
        if not self.is_empty():
            dequeued_item = self.items.pop(0)
            print(f"Dequeued: {dequeued_item}")
            return dequeued_item
        else:
            print("Queue is empty")

    def front(self):
        if not self.is_empty():
            return self.items[0]
        else:
            return "Queue is empty"

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

# Exemplo de uso
queue = Queue()
queue.enqueue(1)
queue.enqueue(2)
queue.enqueue(3)
print(queue.dequeue())  # Output: 1
print(queue.front())    # Output: 2
print(queue.is_empty()) # Output: False
print(queue.size())     # Output: 2
```

## Listas Ligadas (Linked Lists)

### O que é uma Lista Ligada?

Uma lista ligada é uma coleção de nós onde cada nó contém um valor e um ponteiro para o próximo nó na lista.

### Operações Básicas

- **append**: Adiciona um nó ao final da lista.
- **prepend**: Adiciona um nó ao início da lista.
- **delete_with_value**: Remove o primeiro nó que contém o valor especificado.

### Exemplo de Código em Python

```python
class Node:
    def __init__(self, data=None):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
            print(f"Appended {data} as head")
            return
        last_node = self.head
        while last_node.next:
            last_node = last_node.next
        last_node.next = new_node
        print(f"Appended {data}")

    def prepend(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node
        print(f"Prepended {data}")

    def delete_with_value(self, data):
        if self.head is None:
            print("List is empty")
            return
        if self.head.data == data:
            self.head = self.head.next
            print(f"Deleted head with value {data}")
            return
        current_node = self.head
        while current_node.next and current_node.next.data != data:
            current_node = current_node.next
        if current_node.next is None:
            print(f"Value {data} not found in list")
            return
        current_node.next = current_node.next.next
        print(f"Deleted node with value {data}")

    def print_list(self):
        current_node = self.head
        while current_node:
            print(current_node.data)
            current_node = current_node.next

# Exemplo de uso
ll = LinkedList()
ll.append(1)
ll.append(2)
ll.append(3)
ll.prepend(0)
ll.print_list()
ll.delete_with_value(2)
ll.print_list()
```

### Operações com Lista Ligada

1. **`append(data)`**: Adiciona um nó ao final da lista.
2. **`prepend(data)`**: Adiciona um nó ao início da lista.
3. **`delete_with_value(data)`**: Remove o primeiro nó que contém o valor especificado.
4. **`print_list()`**: Imprime todos os elementos da lista.

### Uso

```python
# Exemplo de uso
ll = LinkedList()
ll.append(1)
ll.append(2)
ll.append(3)
ll.prepend(0)
ll.print_list()
ll.delete_with_value(2)
ll.print_list()
```

## Árvores Binárias (Binary Trees)

### O que é uma Árvore Binária?

Uma árvore binária é uma estrutura de dados hierárquica onde cada nó tem no máximo dois filhos, referidos como filho esquerdo e filho direito.

### Operações Básicas

- **insert**: Insere um novo nó na árvore.
- **find**: Procura um nó com o valor especificado.
- **inorder_traversal**: Percorre a árvore em ordem.

### Exemplo de Código em Python

```python
class Node:
    def __init__(self, data):
        self.left = None
        self.right = None
        self.data = data

class BinaryTree:
    def __init__(self):
        self.root = None

    def insert(self, data):
        if self.root is None:
            self.root = Node(data)
            print(f"Inserted {data} as root")
        else:
            self._insert(self.root, data)

    def _insert(self, current_node, data):
        if data < current_node.data:
            if current_node.left is None:
                current_node.left = Node(data)
                print(f"Inserted {data} to the left of {current_node.data}")
            else:
                self._insert(current_node.left, data)
        elif data > current_node.data:
            if current_node.right is None:
                current_node.right = Node(data)
                print(f"Inserted {data} to the right of {current_node.data}")
            else:
                self._insert(current_node.right, data)

    def find(self, data):
        return self._find(self.root, data)

    def _find(self, current_node, data):
        if current_node is None:
            return None
        if data == current_node.data:
            return current_node
        elif data < current_node.data:
            return self._find(current_node.left, data)
        else:
            return self._find(current_node.right, data)

    def inorder_traversal(self):
        return self._inorder_traversal(self.root, [])

    def _inorder_traversal(self, current_node, traversal):
        if current_node:
            traversal = self._inorder_traversal(current_node.left, traversal)
            traversal.append(current_node.data)
            traversal = self._inorder_traversal(current_node.right, traversal)
        return traversal

# Exemplo de uso
bt = BinaryTree()
bt.insert(5)
bt.insert(3)
bt.insert(7)
bt.insert(1)
bt.insert(4)
bt.insert(6)
bt.insert(8)
print(bt.inorder_traversal())  # Output: [1, 3, 4, 5, 6, 7, 8]
```

### Operações com Árvores Binárias

1. **`insert(data)`**: Insere um novo nó na árvore.
2. **`find(data)`**: Procura um nó com o valor especificado.
3. **`inorder_traversal()`**: Percorre a árvore em ordem.

### Uso

```python
# Exemplo de uso
bt = BinaryTree()
bt.insert(5)
bt.insert(3)
bt.insert(7)
bt.insert(1)
bt.insert(4)
bt.insert(6)
bt.insert(8)
print(bt.inorder_traversal())  # Output: [1, 3, 4, 5, 6, 7, 8]
```

---

Se precisar de mais detalhes ou exemplos específicos, estou à disposição para ajudar!

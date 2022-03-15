# Stacks and Queues
the stacks it's the type of data structures that consists of Nodes, each Node will point to next Node and the stacks have some sethod such as IsEmpty and POP Push and Peek  
the POP method it's same delete the Node in Linked list , and the push method is the same insert in linked list in insert the Node in before Top . the Top it's variable point on first element in the Stacks.

## Stacks follow these concepts:
FILO <br>
First In Last Out
his means that the first item added in the stack will be the last item popped out of the stack.

LIFO <br>
This means that the last item added to the stack will be the first item popped out of the stack.
![image](https://user-images.githubusercontent.com/97642724/158379598-aeffb768-0b00-43c5-b0db-ed22142896c6.png)


example to push 

```
ALOGORITHM push(value)
// INPUT <-- value to add, wrapped in Node internally
// OUTPUT <-- none
   node = new Node(value)
   node.next <-- Top
   top <-- Node

```

examble for POP

```
ALGORITHM pop()
// INPUT <-- No input
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   Node temp <-- top
   top <-- top.next
   temp.next <-- null
   return temp.value

```

example for peek : the peek method will return the top element or node is stack and return null if the satck is empty 

```

ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of top Node in stack
// EXCEPTION if stack is empty

   return top.value

```
example for is empty : this method is return for us true if the stack is have any element and fulse if the stack is empty 

```
ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return top = NULL

```
--------------------------------

##  a Queue

a Queue it'the same stack but in diffrent way it contain some concepts :<br/>
FIFO <br/>
First In First Out :This means that the first item in the queue will be the first item out of the queue.

LILO : Last In Last Out

This means that the last item in the queue will be the last item out of the queue.

![image](https://user-images.githubusercontent.com/97642724/158380908-22562923-b076-439a-a7b9-79c3f8b84b0f.png)


-------------------------- 

the queue have tow pointer first  one it name rear it point in last  element in queue abd second one name of it Front and it point in first element queue


 method in queue :
 IsEmpty : return true if the the stack is notEmpty

 ```
 ALGORITHM isEmpty()
// INPUT <-- none
// OUTPUT <-- boolean

return front = NULL
 ```
Peek :will only be inspecting the front Node of the queue.
```
ALGORITHM peek()
// INPUT <-- none
// OUTPUT <-- value of the front Node in Queue
// EXCEPTION if Queue is empty

   return front.value
```


Dequeue :When you remove an item from a queue

```
ALGORITHM dequeue()
// INPUT <-- none
// OUTPUT <-- value of the removed Node
// EXCEPTION if queue is empty

   Node temp <-- front
   front <-- front.next
   temp.next <-- null

   return temp.value
```

Enqueue :When you add an item to a queue, you use the enqueue action. 
```
ALGORITHM enqueue(value)
// INPUT <-- value to add to queue (will be wrapped in Node internally)
// OUTPUT <-- none
   node = new Node(value)
   rear.next <-- node
   rear <-- node

```


[REFERANCE](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-10/resources/stacks_and_queues.html)





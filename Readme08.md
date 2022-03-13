# Linear Complexity Growth
Big O(oh) notation is used to describe the efficiency of an algorithm or function. This efficiency is evaluated based on 2 factors:

Running Time (also known as time efficiency / complexity)
The amount of time a function needs to complete.

Memory Space (also known as space efficiency / complexity)
The amount of memory resources a function uses to store data and instructions.

Big O’s role in algorithm efficiency is to describe the Worst Case of efficiency an algorithm can have in performing it’s job. It specifically looks at the factors mentioned above, which we often refer to as Space and Time. In order to analyze these limiting factors, we should consider 4 Key Areas for analysis:

1-Input Size <br>
2- Units of Measurement<br>
3-Orders of Growth<br>
4-Best Case, Worst Case, and Average Case<br>

### Input Size
Input Size refers to the size of the parameter values that are read by the algorithm. 

examble
Fibonacci Sequence this function take n as index and return value of index n

### Units of Measurement

In order to quantify the Running Time in our analysis, we will consider Three Measurements of time:
The time in milliseconds from the start of a function execution until it ends.
For the purposes of Big O, we won’t be considering this measurement since different machines will have different individual run times depending on how powerful they are. Regardless, this will always be a measurement of run-time.

The number of operations that are executed.
Think of this as the number of lines of code that are executed from start to finish of a function.

The number of “Basic Operations” that are executed.
“Basic Operation” refers to the operation that is contributing the most to the total running time. This is usually the most time consuming operation within the inner most loop.

### Orders of Growth

We can describe overall efficiency by using the input size n and measuring the overall Units of Space and Time required for the given input size n. As the value of n grows, the Order of Growth represents the increase in Running Time or Memory Space.

![image](https://user-images.githubusercontent.com/97642724/156256720-a59fe00c-0d47-46ba-a32d-eeece4d07906.png)


![image](https://user-images.githubusercontent.com/97642724/156256795-79c6d1ba-8340-46a1-987e-7cd66e37fa95.png)

Constant Complexity means that no matter what inputs are thrown at our algorithm, it always uses the same amount of time or space. The number 1 is used to represent a constant value. The actual number of units will most likely be greater than 1, we round this number down to 1 to represent our estimate of complexity that is independant of n.

This algorithm has an O(1) constant efficiency, no matter the size of a or b, this function simply returns the sum of those 2 numbers.

examble 

```
ALGORITHM Sum(number a, number b)

   number val <-- a + b
   return val

```


### Worst Case, Best Case, Average Case

Even though Big O describes the Worst Case for algorithm efficiency, we can still think about Best and Average cases. Each of these cases could be analyzed as we consider the overall question: As inputs n fluctuate in size and order, how does this affect our orders of Growth?

Worst Case: The efficiency for the worst possible input of size n
This case runs the longest for all possible inputs of n. This assumes that if we were sorting values, inputs are completely unsorted and searched values either don’t exist or are at the last to be searched.

Best Case: The efficiency for the best possible input of size n
This case runs the quickest for all possible inputs of n. In the case of sorting, this assumes that values are sorted, and so searched-for values are easy to find.

Average Case: The efficiency for a “typical” or “random” input of size n.
The average case makes a typical assumption about the possible inputs of size ‘n’ and how they might affect efficiency. This is NOT the best case and worst case averaged together.

![image](https://user-images.githubusercontent.com/97642724/156257097-e47a9664-cb7a-4461-83ae-2004e22073ae.png)

-----------------------------------
# Linked Lists

A Linked List is a sequence of Nodes , thath connected to each other , we have many type of linked list :

1- single linked list : in this type we have pointer to point to next node and each node contain pointer and value of linked list  

2- Doubly  linked list : in this type we have pointer to point to next node and pointer to point to previous node .

the Linked list contain some Node 
1- head : it point in first node in linklist and if the linklist is empty it will be null

2- tail : it point in last node in linked list and if the linklist have one node it will be head=tail

![image](https://user-images.githubusercontent.com/97642724/158078666-c605b06a-5fbf-4129-82e2-0e7d1dd5c574.png)


in linkedList we have some method : 

1- insert : this method it take the value and insert it in first element .

2- append : this method it take the value and add it after last element in link lsit

3- include :this method it take the value and check if the linked list have the value it will be return true if the value exists and false if the value not exists.

4 - insert before :this method it take the before value and value it will add the value before the before value.

5 -insert after : this method it take the after value and value it will be add the value after the after value.














































 # [Resourses](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/big_oh.html)
 
 # [Resourses](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/singly_linked_list.html)
### Variables :

#### thear  variables have many kinds : <br/> 
1- Instance Variables : this variabels is it not declear with  static keyword  such as 
` public int count` <br/>

2- class  Variables  : A class variable is any field declared with the  static modifier this tells the compiler that there is exactly one copy of this variable in existence  such as

`static int count = 6`

3 -Local Variables : it the Variables that declear to store an object such as 

`int count = 0`

4- Parameters : the parameter i define it , it's the passing value inside function such as 

`public static void main(String[] args ` the args is a parameter

#### Naming of variables :
the name of variables shuold not contains this folowing ...

1- the Name of variables not contain space .
2-  must the name of variables start with cahr not a sign  or symbol.
3 - the name of variables are case-sensitive.
4 - cannet use the reserved words.

### Operator:

the Operator is a mathematical symbole to do calculations as the folowing table is the symbol of java:

![image](https://user-images.githubusercontent.com/97642724/155745820-f6b2657e-b8b8-44c0-b785-9de198197c11.png)

### Expressions :

An expression is a construct made up of variables, operators, and method invocations, which are constructed according to the syntax of the language, that evaluates to a single value

 **examble :**
 
 ```
 int cadence = 0;
anArray[0] = 100;
System.out.println("Element 1 at index 0: " + anArray[0]);

int result = 1 + 2; // result is now 3
if (value1 == value2) 
    System.out.println("value1 == value2");
 ```
 
### Statements:

we have many Statements such as Assignment expressions ,Any use of ++ or --,Method invocations
,Object creation expressions and declaration statement

**examble**

``
// assignment statement
aValue = 8933.234;
// increment statement
aValue++;
// method invocation statement
System.out.println("Hello World!");
// object creation statement
Bicycle myBike = new Bicycle();
``

### Blocks: 
A block is a group of zero or more statements between balanced braces and can be used anywhere a single statement is allowed .
**examble**

```
class BlockDemo {
     public static void main(String[] args) {
          boolean condition = true;
          if (condition) { // begin block 1
               System.out.println("Condition is true.");
          } // end block one
          else { // begin block 2
               System.out.println("Condition is false.");
          } // end block 2
     }
}

```

### Control Flow Statements :

The statements inside your source files are generally executed from top to bottom, in the order that they appear the type of the control flow statments is `if-then-else, switch
and looping statements (for, while, do-while), and the branching statements (break, continue, return)`.



[resources](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/index.html)






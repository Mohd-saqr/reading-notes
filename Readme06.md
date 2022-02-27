# Java Primitives versus Objects

##  Java Type System :
ava has a two-fold type system consisting of primitives such as int , and Every object contains a single value of the corresponding primitive type.
examble

```
Integer j = 1;          
int i = new Integer(1);

```

## Pros and Cons

The decision what object is to be used is based on some point :

1- what application performance we try to achieve .

2- how much available memory we have

3 - what default values ​​we should handle.

## Single Item Memory Footprint

the variable is usage in memory as folowing :
```
boolean – 1 bit
byte – 8 bits
short, char – 16 bits
int, float – 32 bits
long, double – 64 bits
```

## Memory Footprint for Arrays
The situation becomes more interesting if we compare how much memory occupy arrays of the types under consideration.

![array setaution](https://www.baeldung.com/wp-content/uploads/2018/08/plot-memory-bits.gif)

```
long, double: m(s) = 128 + 64 s
short, char: m(s) = 128 + 64 [s/4]
byte, boolean: m(s) = 128 + 64 [s/8]
the rest: m(s) = 128 + 64 [s/2]
```

## Performance
he performance of a Java code is quite a subtle issue, it depends very much on the hardware on which the code runs, on the compiler that might perform certain optimizations, on the state of the virtual machine, on the activity of other processes in the operating system.

----------------------------

## Exceptions

### What Is an Exception?

the exception is an event which which occurs during execution of a program thats means when i run my program and see some problem it's the exception;

the call stack :

![CallStack](https://docs.oracle.com/javase/tutorial/figures/essential/exceptions-callstack.gif);


## The Catch or Specify Requirement
Valid Java programming language code must honor the Catch or Specify Requirement.

a try statement  it can handel the exception and th catch statement catchs error 

examble 

```
try{
    system.out.pritnln("Hallo world")
}
catch(Exception e){

}
```

## How to Throw Exceptions
any code in java can throw an exception , and can we  create  own exception.

The throw Statement:
 All methods use the throw statement to throw an exception. The throw statement requires a single argument: a throwable object. Throwable objects are instances of any subclass of the Throwable class. Here's an example of a throw statement.

```
public Object pop() {
    Object obj;

    if (size == 0) {
        throw new EmptyStackException();
    }

    obj = objectAt(size - 1);
    setObjectAt(size - 1, null);
    size--;
    return obj;
}
```

## Throwable Class and Its Subclasses
The objects that inherit from the Throwable class include direct descendants (objects that inherit directly from the Throwable class)
the The Throwable class in picture belw :
![Throwable class](https://docs.oracle.com/javase/tutorial/figures/essential/exceptions-throwable.gif)

## Error Class
When a dynamic linking failure or other hard failure in the Java virtual machine occurs, the virtual machine throws an Error. Simple programs typically do not catch or throw Errors.

## The try-with-resources Statement
The try-with-resources statement is a try statement that declares one or more resources. A resource is an object that must be closed after the program is finished with it.

## Unchecked Exceptions — The Controversy
Because the Java programming language does not require methods to catch or to specify unchecked exceptions (RuntimeException, Error, and their subclasses).

## Advantages of Exceptions

Advantage 1: Separating Error-Handling Code from "Regular" Code

examble
```
errorCodeType readFile {
    initialize errorCode = 0;
    
    open the file;
    if (theFileIsOpen) {
        determine the length of the file;
        if (gotTheFileLength) {
            allocate that much memory;
            if (gotEnoughMemory) {
                read the file into memory;
                if (readFailed) {
                    errorCode = -1;
                }
            } else {
                errorCode = -2;
            }
        } else {
            errorCode = -3;
        }
        close the file;
        if (theFileDidntClose && errorCode == 0) {
            errorCode = -4;
        } else {
            errorCode = errorCode and -4;
        }
    } else {
        errorCode = -5;
    }
    return errorCode;
}
```
Advantage 2: Propagating Errors Up the Call Stack

examble 

```
method1 {
    call method2;
}

method2 {
    call method3;
}

method3 {
    call readFile;
}
```

Advantage 3: Grouping and Differentiating Error Types
Examble

```
catch (IOException e) {
    // Output goes to System.err.
    e.printStackTrace();
    // Send trace to stdout.
    e.printStackTrace(System.out);
}
```
-----------------------------

## Scanning
### Breaking Input into Tokens
Objects of type Scanner are useful for breaking down formatted input into tokens and translating individual tokens according to their data type.

By default, a scanner uses white space to separate tokens. (White space characters include blanks, tabs, and line terminators. For the full list, refer to the documentation for Character.isWhitespace.) To see how scanning works, let's look at ScanXan, a program that reads the individual words in xanadu.txt and prints them out, one per line.

examble 

```
import java.io.*;
import java.util.Scanner;

public class ScanXan {
    public static void main(String[] args) throws IOException {

        Scanner s = null;

        try {
            s = new Scanner(new BufferedReader(new FileReader("xanadu.txt")));

            while (s.hasNext()) {
                System.out.println(s.next());
            }
        } finally {
            if (s != null) {
                s.close();
            }
        }
    }
}
```

# Resourses

[Java Primitives versus Objects](https://www.baeldung.com/java-primitives-vs-objects)

[The Java™ Tutorials
](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)

[Scanning](https://docs.oracle.com/javase/tutorial/essential/io/scanning.html)



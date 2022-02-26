# Packages and Import
the Package  is similar directory , put the directory contains many extention  file such as
.exe , .png etc.. .
the  Package  contain the java file and i declare when  define i Java program and i name the packages you want to use from other libraries in an import statement.

------------------------------------------------------------------------------

### Package declaration

i must be declare the Package in java source .
i canimport statements, which allow you to specify classes from other packages.

the Default package it's possible to omit the package declaration.

-----------------------------------------------------

### Package declaration syntax

The statement order is as follows. Comments can go anywhere.

1- Package statment (optional).
2- Imports (optional).
3- Class or interface definitions.

i can use one of thes to declare the any package example
```
package illustration;

import java.awt.*;

public class Drawing {
    . . .
}

```

-------------------------------

### Imports: three options

the JOptionPane class is in the swing package which is located in the javax package , we use the wildcard character (*) to use all classes in javax.swing examble 

```
import javax.swing.*;  to use all classes in the java swing 

class ImportTest {
    public static void main(String[] args) {
        JOptionPane.showMessageDialog(null, "Hi");
        System.exit(0);
    }
}

```

we can use a JOptionPane to make it visible examble 

```

import javax.swing.JOptionPane;  
class ImportTest {
    public static void main(String[] args) {
        JOptionPane.showMessageDialog(null, "Hi");
        System.exit(0);
    }
}
```
----------------------------------------------------------------------------

### Common imports

in the java language in contain 166 packages containing 3279 classes , but the most common uses the GUI program as it show blew 

`````
import java.awt.*;	Common GUI elements.
import java.awt.event.*;	The most common GUI event listeners.
import javax.swing.*;	More common GUI elements. Note "javax".
import java.util.*;	Data structures (Collections), time, Scanner, etc classes.
import java.io.*;	Input-output classes. aswe learned in class 3 
import java.text.*;	Some formatting classes.
import java.util.regex.*;	Regular expression classes.

`````

### NetBeans creates packages by default
the name of project it used by duflute for name of package but we can change it , and the dirctory name (folder) create with the name of package .
the package declaration is automatically inserted into each new source file it creates.


### NetBeans will create your imports
the NetBeans will import automatically when i use some method in the class such as if i 
use system.out.println() the NetBeans will import class java.utils

-------------------------------------------------------------

### Static imports in Java 5

we can use static Keyword to be referenced without qualifying them with a class name examble 

``
import static java.awt.Color
``
we can use the color method without write Color.red examble 

    Color background = RED;

---------------------------------------------------------------------------------------------------
# Java Loops

the loop it used to lopoing inside the arry and String and Object there are many thpe of loop 
1- for loop
2- for-each loop
3- While loop
4- Do-While loop

exambel for each one 

for loop 

```
for(int index =0 ; index <10; index ++){
code to do..
}

```

for-each loop 
the for-each returned the arry and it's the function ..

```
 int [] newArr = arr.forEach(element =>{
     return element +=1
 })

```
While loop 

the while loop keep looping even the condetion it be false 
```
int count =0;
while(count<10){
    count ++ // it must to put the inctement becuse when we didn't put it we will have infenit loop .
}
```

Do-While Loop
similar then while loop but in deferent way 

```
do{
    code to do ..
}

while (condition)



```

[Referance1](https://www.baeldung.com/java-loops)

[Referance2](https://perso.ensta-paris.fr/~diam/java/online/notes-java/language/10basics/import.html)


[Referance3](https://www.w3schools.com/java/java_while_loop.asp)

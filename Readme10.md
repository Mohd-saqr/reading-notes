# Don’t Repeat Yourself :

 is a principle of software development aimed at reducing repetition of software patterns, replacing it with abstractions or using data normalization to avoid redundancy. 

 that mean keap your code clean 


 exampel

 ```
 int x =0;
 int  z =0 ;
 int y = 0;

 if(x<z>){
     z++
 }

 if(y<z){
     z++
 }

 you can reblace z++ becouse you now repat your self 

 public void increament (int var){
     var++
 } 

 and the code become 

  int x =0;
 int  z =0 ;
 int y = 0;

 if(x<z>){
   increament(z)
 }

 if(y<z){
     increament(z)
 }

 ```


 # Rule of three (computer programming)

 is a code refactoring rule of thumb to decide when similar pieces of code should be refactored to avoid duplication. It states that two instances of similar code do not require refactoring, but when similar code is used three times, it should be extracted into a new procedure. 

Rule of Three: if a class defines any of these, it must define all three:
1- Destructor
2- Copy constructor
3- Copy assignment operator



# A minimum viable product (MVP)

A minimum viable product (MVP) is a version of a product with just enough features to be usable by early customers who can then provide feedback for future product development.

A focus on releasing an MVP means that developers potentially avoid lengthy and (ultimately) unnecessary work. Instead, they iterate on working versions and respond to feedback, challenging and validating assumptions about a product's requirements. The term was coined and defined in 2001 by Frank Robinson and then popularized by Steve Blank and Eric Ries. It may also involve carrying out market analysis beforehand. The MVP is analogous to experimentation in the scientific method applied in the context of validating business hypotheses. It is utilized so that prospective entrepreneurs would know whether a given business idea would actually be viable and profitable by testing the assumptions behind a product or business idea.The concept can be used to validate a market need for a product and for incremental developments of an existing product. As it tests a potential business model to customers to see how the market would react, it is especially useful for new/startup companies who are more concerned with finding out where potential business opportunities exist rather than executing a prefabricated, isolated business model.


[Referance](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) <br>
[Referance](https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming))<br/>
[Referance](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)

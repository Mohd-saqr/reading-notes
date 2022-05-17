# GraphQL @connection

### Has Many relationship

The @hasOne and @hasMany directives do not support referencing a model which then references the initial model via @hasOne or @hasMany if DataStore is enabled.


Create a one-directional one-to-many relationship between two models using the @hasMany directive.

### Many-to-many relationship

Create a many-to-many relationship between two models with the @manyToMany directive. Provide a common relationName on both models to join them into a many-to-many relationship.

Under the hood, the @manyToMany directive will create a "join table" named after the relationName to facilitate the many-to-many relationship. This generates queries and mutations that allow you to retrieve the related Comment records from the source Post record and vice versa.



## Using CompletableFuture as a Simple Future

First of all, the CompletableFuture class implements the Future interface, so we can use it as a Future implementation, but with additional completion logic.

For example, we can create an instance of this class with a no-arg constructor to represent some future result, hand it out to the consumers, and complete it at some time in the future using the complete method. The consumers may use the get method to block the current thread until this result is provided.


To spin off the computation, we use the Executor API. This method of creating and completing a CompletableFuture can be used together with any concurrency mechanism or API, including raw threads.

Notice that the calculateAsync method returns a Future instance.

We simply call the method, receive the Future instance, and call the get method on it when we're ready to block for the result.



### CompletableFuture with Encapsulated Computation Logic

Static methods runAsync and supplyAsync allow us to create a CompletableFuture instance out of Runnable and Supplier functional types correspondingly.
The Supplier interface is a generic functional interface with a single method that has no arguments and returns a value of a parameterized type.

This allows us to provide an instance of the Supplier as a lambda expression that does the calculation and returns the result



### Combining Futures

he best part of the CompletableFuture API is the ability to combine CompletableFuture instances in a chain of computation steps.

The result of this chaining is itself a CompletableFuture that allows further chaining and combining. This approach is ubiquitous in functional languages and is often referred to as a monadic design pattern.

In the following example we use the thenCompose method to chain two Futures sequentially.



### Difference Between thenApply() and thenCompose()

 thenApply()
We can use this method to work with a result of the previous call. However, a key point to remember is that the return type will be combined of all calls.

So this method is useful when we want to transform the result of a CompletableFuture call


###  thenCompose()

he thenCompose() method is similar to thenApply() in that both return a new Completion Stage. However, thenCompose() uses the previous stage as the argument. It will flatten and return a Future with the result directly, rather than a nested future as we observed in thenApply():




 # Resources


 [One-to-many and many-to-one connections using GraphQL in AWS Amplify](https://docs.amplify.aws/cli/graphql/data-modeling/#has-many-relationship)
 
  [AWS Amplify Kool-Aid](https://aws.amazon.com/amplify/)

 [CompletableFuture in Java ](https://www.baeldung.com/java-completablefuture)
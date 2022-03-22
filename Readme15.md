# Working with Relationships in Spring Data REST
the Relationships it's same connnect each table with gethor , if we have an example such as we have a resturant and each resturant has an location the realation between them OneToOne becuse each resturant has one location but if we have another example such as a student have a many subject in this example the relation is oneToMany .

### hwo to use the Relationships in spring 
we can use the notation @JoinColumn and thee realation notation     @ManyToOne or @OnToOne
etc 

example
To exemplify a one-to-many relationship, let's add a new Book entity that will represent the “many” end of a relationship with the Library entity:
the model
`````
@Entity
public class Book {

    @Id
    @GeneratedValue
    private long id;
    
    @Column(nullable=false)
    private String title;
    
    @ManyToOne
    @JoinColumn(name="library_id")
    private Library library;
    
    // standard constructor, getter, setter
}
`````
Let's add the relationship to the Library class as well:

```
public class Library {
 
    //...
 
    @OneToMany(mappedBy = "library")
    private List<Book> books;
 
    //...
 
}

```

Many-to-Many Relationship :A many-to-many relationship is defined using @ManyToMany annotation, to which we can add @RestResource.

example 
model
````
@Entity
public class Author {

    @Id
    @GeneratedValue
    private long id;

    @Column(nullable = false)
    private String name;

    @ManyToMany(cascade = CascadeType.ALL)
    @JoinTable(name = "book_author", 
      joinColumns = @JoinColumn(name = "book_id", referencedColumnName = "id"), 
      inverseJoinColumns = @JoinColumn(name = "author_id", 
      referencedColumnName = "id"))
    private List<Book> books;

    //standard constructors, getters, setters
}
````
Let's add the association in the Book class as well:

````
public class Book {
 
    //...
 
    @ManyToMany(mappedBy = "books")
    private List<Author> authors;
 
    //...
}
````

# Integration Testing in Spring
in this section we use the Junit 5 or 4 to test Spring work by annotation in the test method

how to use spring test 

JUnit 5 defines an extension interface through which classes can integrate with the JUnit test.

We can enable this extension by adding the @ExtendWith annotation to our test classes and specifying the extension class to load. To run the Spring test, we use SpringExtension.class.

We'll also need the @ContextConfiguration annotation to load the context configuration and bootstrap the context that our test will use.

example :

```````
@ExtendWith(SpringExtension.class)
@ContextConfiguration(classes = { ApplicationConfig.class })
@WebAppConfiguration
public class GreetControllerIntegrationTest {
    ....
}
```````


# resourses

[Integration Testing in Spring](https://www.baeldung.com/integration-testing-in-spring)<br/>
[https://www.baeldung.com/spring-data-rest-relationships](https://www.baeldung.com/spring-data-rest-relationships)






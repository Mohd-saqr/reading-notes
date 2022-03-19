# JPA - (Java Persistence API)
the JPA best framework that abstracts all of the complexity needed for you interact with data base the most implemenlation of it is Hibernate . <br/>

Hibernate it's a shell it take any java object and map in data base .


## How to use JPA

first Define a Simple Entity:
Spring Data JPA focuses on using JPA to store data in a relational database. Its most compelling feature is the ability to create repository implementations automatically, at runtime, from a repository interface.


````
package com.example.accessingdatajpa;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class Customer {

  @Id
  @GeneratedValue(strategy=GenerationType.AUTO)
  private Long id;
  private String firstName;
  private String lastName;

  protected Customer() {}

  public Customer(String firstName, String lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
  }

  @Override
  public String toString() {
    return String.format(
        "Customer[id=%d, firstName='%s', lastName='%s']",
        id, firstName, lastName);
  }

  public Long getId() {
    return id;
  }

  public String getFirstName() {
    return firstName;
  }

  public String getLastName() {
    return lastName;
  }
}
````

second Create Simple Queries
: 

````
package com.example.accessingdatajpa;

import java.util.List;

import org.springframework.data.repository.CrudRepository;

public interface CustomerRepository extends CrudRepository<Customer, Long> {

  List<Customer> findByLastName(String lastName);

  Customer findById(long id);
}

````

# CrudRepository, JpaRepository, and PagingAndSortingRepository in Spring Data

The goal of Spring Data repository abstraction is to significantly reduce the
amount of boilerplate code required to implement data access layers for
various persistence stores.

![image](https://user-images.githubusercontent.com/97642724/159139511-75fcdb2d-43b0-452c-91df-a293922680e0.png)



## CrudRepository
the CrudRepository it had some methd and we can use it to control on data base with out useing querys or adding , find , delete etc ..

```
public interface CrudRepository<T, ID extends Serializable>
  extends Repository<T, ID> {

    <S extends T> S save(S entity);

    T findOne(ID primaryKey);

    Iterable<T> findAll();

    Long count();

    void delete(T entity);

    boolean exists(ID primaryKey);
}
```

## PagingAndSortingRepository

```
public interface PagingAndSortingRepository<T, ID extends Serializable> 
  extends CrudRepository<T, ID> {

    Iterable<T> findAll(Sort sort);

    Page<T> findAll(Pageable pageable);
}
```

## JpaRepository
```
public interface JpaRepository<T, ID extends Serializable> extends
  PagingAndSortingRepository<T, ID> {

    List<T> findAll();

    List<T> findAll(Sort sort);

    List<T> save(Iterable<? extends T> entities);

    void flush();

    T saveAndFlush(T entity);

    void deleteInBatch(Iterable<T> entities);
}
```

# Resourses
[CrudRepository, JpaRepository, and PagingAndSortingRepository in Spring Data ](https://www.baeldung.com/spring-data-repositories) <br/>
[Accessing Data with JPA
 ](https://spring.io/guides/gs/accessing-data-jpa/) <br/>
 [Amigoscode](https://www.youtube.com/watch?v=8SGI_XS5OPw&t=935s)
# Hibernate Many to Many Annotation Tutorial
In our database we create many tables and many of them may be associated with each other. At higher lever, these associations can be classified into one-to-one, one-to-many and many-to-many. These associations can be either unidirectional or bidirectional mappings. Hibernate provides support to all these associations.

and in this reading we learn how to use many to many

![image](https://user-images.githubusercontent.com/97642724/161450545-cce58d96-e5ac-4806-af56-27a2b499fba7.png)

The model classes Employee and Project need to be created with JPA annotations:
### The Model Classes
```
@Entity
@Table(name = "Employee")
public class Employee { 
    // ...
 
    @ManyToMany(cascade = { CascadeType.ALL })
    @JoinTable(
        name = "Employee_Project", 
        joinColumns = { @JoinColumn(name = "employee_id") }, 
        inverseJoinColumns = { @JoinColumn(name = "project_id") }
    )
    Set<Project> projects = new HashSet<>();
   
    // standard constructor/getters/setters
}
```



```
@Entity
@Table(name = "Project")
public class Project {    
    // ...  
 
    @ManyToMany(mappedBy = "projects")
    private Set<Employee> employees = new HashSet<>();
    
    // standard constructors/getters/setters   
}
```




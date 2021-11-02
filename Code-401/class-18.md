# Web App Security and many to many relation

in the previous week we talk about one to one relation and many to one relation, but what if we want to have many to many relation?

imagine that we have a user and a course, and we want to have many to many relation between them, so we can have many users in a course, and many courses in a user.

![many to many relation](https://fmhelp.filemaker.com/help/18/fmp/en/FMP_Help/images/relational.07.06.1.png)

to set up the data base we use the following command:

```java
@Entity
@Table(name = "User")
public class User {
    // ...

    @ManyToMany(cascade = { CascadeType.ALL })
    @JoinTable(
        name = "User_Course",
        joinColumns = { @JoinColumn(name = "user_id") },
        inverseJoinColumns = { @JoinColumn(name = "course_id") }
    )
    Set<Course> courses = new HashSet<>();

    // standard constructor/getters/setters
}
@Entity
@Table(name = "Courses")
public class Courses {
    // ...

    @ManyToMany(mappedBy = "courses")
    private Set<user> users = new HashSet<>();

    // standard constructors/getters/setters
}
```

And by following this command we have created entity classes for both user and course, and we have created a table for the relation between them.

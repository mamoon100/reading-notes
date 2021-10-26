# Related Resources and Integration Testing

As we know that the Sql is relational database so what that means is we can build relation between the tables so let's see how to do it using spring boot.

First of all we have one on one relation an we can built it using **RestResource** annotation.

```java
@Entity
public class Library {

    @Id
    @GeneratedValue
    private long id;

    @Column
    private String name;

    @OneToOne
    @JoinColumn(name = "address_id")
    @RestResource(path = "libraryAddress", rel="address")
    private Address address;

    // standard constructor, getters, setters
}
```

```java
@Entity
public class Address {

    @Id
    @GeneratedValue
    private long id;

    @Column(nullable = false)
    private String location;

    @OneToOne(mappedBy = "address")
    private Library library;

    // standard constructor, getters, setters
}
```

Second we have one to many relation so we can built it using **OneToMany** annotation.

```java
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
```

```java
public class Library {

    //...

    @OneToMany(mappedBy = "library")
    private List<Book> books;

    //...

}
```

The third relation is many to many relation so we can built it using **ManyToMany** annotation.

```java
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
```

```java

public class Book {

    //...

    @ManyToMany(mappedBy = "books")
    private List<Author> authors;

    //...
}
```

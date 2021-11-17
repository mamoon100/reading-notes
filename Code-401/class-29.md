# Room

What is room?
The Room persistence library provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite. In particular, Room provides the following benefits:

1. Compile-time verification of SQL queries.
2. Convenience annotations that minimize repetitive and error-prone boilerplate code.
3. Streamlined database migration paths.

to use Room, you need to add the following dependency to your app:

```groovy
implementation "androidx.room:room-runtime:2.3.0"
annotationProcessor "androidx.room:room-compiler:2.3.0"
```

There are three main components of Room:

- The Room database class.
- The Room DAO class.
- The Room Entity class.

The dao that provide method that your app can user query to insert, update, delete, and query data from the database, so we will be using query and not the app will took care of like spring boot.

How to define entity in Room?

```java
@Entity
public class User {
    @PrimaryKey(autoGenerate = true)
    public int id;
    public String name;
    public String email;
}
```

How to define DAO in Room?

```java
@Dao
public interface UserDao {
    @Insert
    void insert(User user);

    @Update
    void update(User user);

    @Delete
    void delete(User user);

    @Query("SELECT * FROM user")
    LiveData<List<User>> getAll();
}


```

How to define database in Room?

```java
@Database(entities = {User.class}, version = 1)
public abstract class AppDatabase extends RoomDatabase {
    public abstract UserDao userDao();
}
```

How to use Room?

```java
AppDatabase db = Room.databaseBuilder(getApplicationContext(),
        AppDatabase.class, "database-name").build();
```

And then you can get dao by calling:

```java
UserDao userDao = db.userDao();
List<User> users = userDao.getAll();
```

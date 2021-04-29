# Android Room

Room is a technology very similar to Spring JPA of other db interfaces. 
It works by defining models that are annotated as entities that are then created within a local SQlite DB made accessible through Rooms DAOs(Data Access Objects).

See Save data in a local database using Room :https://developer.android.com/training/data-storage/room

## Example entity

    @Entity
    public class User {
        @PrimaryKey
        public int uid;

        @ColumnInfo(name = "first_name")
        public String firstName;

        @ColumnInfo(name = "last_name")
        public String lastName;
    }

## Example DAO

Note in the below DAO that queries are also being defined to take in dynamic values with ```:valueName```

    @Dao
    public interface UserDao {
        @Query("SELECT * FROM user")
        List<User> getAll();

        @Query("SELECT * FROM user WHERE uid IN (:userIds)")
        List<User> loadAllByIds(int[] userIds);

        @Query("SELECT * FROM user WHERE first_name LIKE :first AND " +
            "last_name LIKE :last LIMIT 1")
        User findByName(String first, String last);

        @Insert
        void insertAll(User... users);

        @Delete
        void delete(User user);
    }

### Additional information

* Defining data using Room entities: https://developer.android.com/training/data-storage/room/defining-data
* Define relationships between objects: https://developer.android.com/training/data-storage/room/relationships
* Accessing data using Room DAOs: https://developer.android.com/training/data-storage/room/accessing-data
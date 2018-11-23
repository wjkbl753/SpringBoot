> 有时候系统预置的方法不能满足要求，那么我们需要可以自定义sql语句

```java
 //原生sql方式
public interface BookRepository extends JpaRepository<Book,Long> {
    @Query(value = "select * from book where length(name)>?1",nativeQuery = true)
    List<Book> findByJP(int len);
}
```

```java
//jpql方式
public interface BookRepository extends JpaRepository<Book,Long> {
    @Query("from Book  where length(name)>?1")
    List<Book> findByJP(int len);
}
```
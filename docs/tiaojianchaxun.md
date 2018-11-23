## 按一个条件查询：
```java
public interface BookRepository extends JpaRepository<Book,Long> {
    List<Book> findByAuthor(String author);
}
```
```java
/**
* 根据作者查询数据
*/
@Test
public void findByAuthor(){
    List<Book> book = bookRepository.findByAuthor("小明");
    System.out.println(book);
}

```

## 按多个条件查询：
```java
public interface BookRepository extends JpaRepository<Book,Long> {
    List<Book> findByAuthorAndStatus(String author,int status);
}
```
```java
/**
* 根据作者和状态查询数据
*/
@Test
public void findByAuthorAndStatus(){
    List<Book> books = bookRepository.findByAuthorAndStatus("小明", 0);
    System.out.println(books);
}
```

## 其他接口方式举例：
```java
public interface BookRepository extends JpaRepository<Book,Long> {
    // 包含
    List<Book> findByDescriptionContains(String key);
    //以xxx结尾
    List<Book> findByDescriptionEndingWith(String key);
}
```

!> 其他更详细具体使用参考官方文档 
[https://docs.spring.io/spring-data/jpa/docs/1.11.16.RELEASE/reference/html/#jpa.query-methods](https://docs.spring.io/spring-data/jpa/docs/1.11.16.RELEASE/reference/html/#jpa.query-methods)

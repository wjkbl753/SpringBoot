## 修改
`BookRepository`
```java
@Transactional
@Modifying
@Query("update Book b set b.status=?1 where id=?2")
int updateByJP(int status,long id);
```
`Test`
```java
 @Test
public void updateByJp(){
    int i = bookRepository.updateByJp(3,1);
    System.out.println(i);
}
```

!> 次案例只是测试，实际开发 @Transactional 一般加到业务层，开启事务

## 删除
`BookRepository`
```java
@Transactional
@Modifying
@Query("delete from Book b where b.id=?1")
int deleteByJp(long id);
```
`Test`
```java
@Test
public void deleteByJp(){
    int i = bookRepository.deleteByJp(1l);
    System.out.println(i);
}
```
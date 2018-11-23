## 创建Repository：

`BookRepository`
```java
public interface BookRepository extends JpaRepository<Book,Long> {
}
```         

## 基本crud：
```java
@RunWith(SpringRunner.class)
@SpringBootTest
public class DemoApplicationTests {
    @Autowired
    private BookRepository bookRepository;
    /**
     * 查询所有数据
     */
    @Test
    public void findAll() {
        List<Book> all = bookRepository.findAll();
        System.out.println(all);
    }
    /**
     * 增加一条数据
     */
    @Test
    public void save(){
        Book book = new Book();
        book.setAuthor("小明");
        book.setDescription("haha");
        Book b = bookRepository.save(book);
        System.out.println(b);      //最后结果:这个book里会有生成的id值
    }
    /**
     * 根据id查询一条数据
     */
    @Test
    public void findOne(){
        Book book = bookRepository.findOne(2l);
        System.out.println(book);
    }
    /**
     * 修改
     */
    @Test
    public void update(){
        Book book = new Book();
        book.setId(1);
        book.setAuthor("笑笑");
        Book b = bookRepository.save(book);
        System.out.println(b);
    }
    /**
    * 根据id删除数据
    */
    @Test
    public void delete(){
        bookRepository.delete(2l);
    }
}
```      


```yml
student:
 name: 小明
 age: 20
```
读取：

### 方式一：
```java
@RestController
public class HelloController {

    @Value("${student.name}")
    private String name;
    @Value("${student.age}")
    private String age;

    @RequestMapping("/say")
    public String hello(){
        return "hello springboot";
    }
    @RequestMapping("/student")
    public String student(){
        return "名字:"+name+" 年龄:"+age;
    }
}
```

然后地址栏访问：[http://localhost:8080/student](http://localhost:8080/student)

### 方式二：
创建javabean,把配置中的属性都直接注入到javabean中

`Student`
```java
@Component
@ConfigurationProperties(prefix = "student")
public class Student {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```
`HelloController`
```java
@RestController
public class HelloController {

    @Autowired
    private Student student;

    @Value("${student.name}")
    private String name;
    @Value("${student.age}")
    private String age;

    @RequestMapping("/say")
    public String hello(){
        return "hello springboot";
    }
    @RequestMapping("/student")
    public String student(){
        return "名字:"+name+" 年龄:"+age;
    }

    @RequestMapping("/student2")
    public Student student2(){
        return student;
    }
}
```
然后访问： [http://localhost:8080/student2](http://localhost:8080/student2)

!> 如果idea出现spring boot configuration annotation processor not found in classpath，需要引入pom
```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-configuration-processor</artifactId>
    <optional>true</optional>
</dependency>
```

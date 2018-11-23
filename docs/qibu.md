## 引入pom

* 我们可以在创建项目时直接勾选jpa选项
* 手动加入pom

```xml
<!-- spring-data-jpa,spring-orm,hibernate相关jar包 -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
<!-- mysql驱动 -->
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
</dependency>
```

## 配置文件
```xml
spring:
  datasource:
    driver-class-name: com.mysql.jdbc.Driver
    url: jdbc:mysql://localhost:3306/book
    username: xxx
    password: xxx
  jpa:
    hibernate:
     <!-- 每次启动服务器会清空数据库表,重新创建  -->
      ddl-auto: create
    show-sql: true
```
## 创建实体
```java
@Data
@Entity
public class Book {
    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    private long id;
    private String name;
    private String author;
    private int status;
    private String description;
}
```

## 启动服务器
就会发现数据库中创建了相应的数据表

- 在数据库表中随便插入一些数据后，重启服务器，观察数据表结果
- 修改  ddl-auto: create 为 ddl-auto: update，重复上面的操作，观察结果
## 导入pom
```xml
<!-- <dependency>
    <groupId>org.mybatis.spring.boot</groupId>
    <artifactId>mybatis-spring-boot-starter</artifactId>
    <version>1.3.1</version>
</dependency> -->

<!-- mybatis-plus -->
<dependency>
    <groupId>com.baomidou</groupId>
    <artifactId>mybatis-plus-boot-starter</artifactId>
    <version>3.0.6</version>
</dependency>
```

## 配置文件

```yml
mybatis:
  mapper-locations: classpath:mapper/*.xml
```

## 启动文件

启动类上开启mapper扫描
```java
@SpringBootApplication
@MapperScan("com.weixin.mapper")
public class DemoApplication {
    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
}
```

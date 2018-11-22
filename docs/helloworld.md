> 之前的项目直接启动springboot，我们发现是404，那是因为我们没有配置访问路径

## 新建restful风格的请求

> 现在新建web包。新建类HelloController

```java
@RestController
public class HelloController {
    @RequestMapping("/say")
    public String hello(){
        return "hello springboot";
    }
}
```

浏览器访问路径： [http://localhost:8080/say](http://localhost:8080/say)之后可以看到结果了


## 新建非restful风格的请求：

* 加入thymeleaf依赖：
 ```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>
 ```

*  新建controller：
```java
@Controller
public class HelloController2 {
    @RequestMapping("/say2")
    public String hello(){
        return "books";
    }
}
```

* 在templates文件夹新建模板页 `books.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"/>      
    <title>Title</title>
</head>
<body>
    <h1>hello books</h1>
</body>
</html>
```
!> springboot是以xml方式解析模板页的，所以<meta> 单标签必须闭合，否则报错

浏览器访问路径： [http://localhost:8080/say2](http://localhost:8080/say2)之后可以看到结果了

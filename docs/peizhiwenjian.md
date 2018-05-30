## @ConfigurationProperties方式

```java
/**
 * 将本类中所有属性和配置文件中相关配置进行绑定
 * 必须是组件@ConfigurationProperties才能生效
 */
@Component
@ConfigurationProperties(prefix = "person")
public class Person {
    private String lastName;
    private Integer age;
    private Boolean boss;
    private Date birth;

    private Map<String,Object> map;
    private List<Object> list;
    private Dog dog;
}
```
`application.yml`
```xml
server:
  port: 8081

person:
  lastName: zhangsan
  age: 18
  boss: false
  birth: 2018/12/12
  map: {k1: v1,k2: 12}
  list:
    - lisi
    - zhangsan
    - zhaoliu
  dog:
    name: 小狗
    age: 2
```

## spring原生方式：
@ConfigurationProperties

```java
public class Person {

    @Value("${person.name}")
    private String lastName;
}
```

>使用场景：

如果需要在某个业务逻辑中获取某个配置文件的值可以使用spring原生方式：

```java
@Controller
public class HelloController {

    @Value("${person.dog.name}")
    private String name;


    @RequestMapping("/hello")
    @ResponseBody
    public String hello(){
        return "hello"+name;
    }
}
```

如果是有专门的bean获取大量配置属性使用@ConfigurationProperties

## 配置类：

SpringBoot推荐使用配置类代替配置文件：

比如：原来想在配置文件中加一个bean，现在的做法是在配置类中加

`配置类`
```java
//需要加注解标识这是一个配置类，用来代替之前的spring配置文件
//bean的id就是方法名，返回值就是容器bean
@Configuration
public class MyAppConfig {
    @Bean
    public Dog helloDog(){
        return new Dog("小狗",2);
    }
}
```

## @PropertySource

所有配置都写到全局配置文件中太大了。我们可以写到另外的配置文件中(但只限于properties文件)

在类上加
@PropertySource(value = {"classpath:person.properties"})

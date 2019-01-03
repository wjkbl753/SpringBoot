## 事务使用

    springboot的事务使用非常简单

### 启动类上开启事务支持
```java
@EnableTransactionManagement
```

### 在需要使用事务的业务层方法上加注解
```java
@Transactional
```
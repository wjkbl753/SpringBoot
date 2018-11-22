配置文件命名：
`application-xxx.yml`

在创建另外两个配置文件： `application-dev.yml` 和 `application-pro.yml`

`application-dev.yml`
```xml
server:
  port: 8081
logging:
  file: logs/dev.log
```
`application-pro.yml`
```xml
server:
  port: 8082
logging:
  file: logs/pro.log
```

在主配置文件`application.yml`中指定使用的配置：
```xml
spring:
  profiles:
    active: dev
```
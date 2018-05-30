Profile是Spring对不同环境提供不同配置功能的支持

1.多profile文件形式：
- application-dev.yml
- application-prod.yml
- appilcation-test.yml

在主配置文件`application.yml`中指定使用的配置：
```xml
spring:
  profiles:
    active: dev
```
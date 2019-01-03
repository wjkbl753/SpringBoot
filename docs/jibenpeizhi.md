## application.properties

```properties
#tomcat服务器配置

#配置监听端口号
server.port=8081
#配置访问路径
server.context-path=/app

#日志配置
logging.level.root=warn
logging.level.com.lrm=debug
logging.file=logs/my.log
```

## 配置文件位置：
springboot生成项目后会在`resources`中直接生成一个配置文件`application.properties`,我们也可以在`resources`文件夹中新建`config`文件夹，里面放入配置文件:`application.properties` 如果两个位置都有配置文件，则两个配置文件中的内容将同时生效，但是如果有冲突，以`config中的配置文件`为准

## yml配置文件

springboot建议使用yml形式的配置文件,看起来更直观,在config文件夹下创建application.yml文件
```yml
server:
  port: 8081
  context-path: /app
logging:
  level:
    root: warn
    com.lrm: debug
  file: logs/my.log
```
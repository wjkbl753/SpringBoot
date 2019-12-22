SpringBoot默认使用 slf4j+logback日志框架

直接使用：
```java
    Logger logger = LoggerFactory.getLogger(getClass());
    logger.trace("*********trace*******");
    logger.debug("*********debug*******");
    logger.info("*********info*******");
    logger.warn("*********warn*******");
    logger.error("*********error*******");
```

!> 从输出结果可以看出，springboot默认的输出级别是info以上(包括info)，那么我们如何修改日志级别？

```xml
<!--  com.woyuno.包下所有日志都是trace级别 -->
logging:
  level:
    com.woyuno: trace
```

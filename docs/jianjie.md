## JPA

jpa(java persistence API,Java持久化API),定义了对象关系映射(object relation mapping,orm)以及实体对象持久化的标准接口，hibernate是实现了jpa的一个orm框架

jpa是一套接口规范，不是一套orm框架

## Spring Data JPA

Spring Data JPA基于JPA进一步简化了数据访问层的实现，它提供了一种类似于声明式编程的方式，开发者只需编写数据访问接口(Repository)，Spring Data JPA就能基于接口中的方法命名自动的生成实现

Spring Data JPA是spring基于orm框架，JPA规范基础上的进一步封装
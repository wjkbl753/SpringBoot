```java
 @GetMapping("/aa")
public String hello(Map map){
    User user = new User();
    user.setUserName("xiaowang");
    user.setBirthday(new Date());
    user.setEmail("sdfs.@q34.com");

    map.put("name","小明");
    map.put("user",user);
    return "hello";
}
```
```html
<div th:object="${user}">
    <div th:text="${name2}"></div>
    <div th:text="*{userName}"></div>
    <div th:text="*{#dates.format(birthday,'yyyy-MM-dd HH:mm:ss')}"></div>
    <div th:text="*{email}"></div>
</div>
```
## 后端代码
```java
@GetMapping("/aa")
public String hello(Map map){
    User user = new User();
    user.setUserName("小明");
    user.setGender("1");
    user.setClassroomId(2);
    map.put("user",user);
    return "hello";
}
```

## 前端代码

```html
<!DOCTYPE html>
<html lang="en" xmlns:th="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
    <form action="">
        <p>
            姓名:
        </p>
        <p>
            <input type="text" th:value="${user.userName}">
        </p>
        <p>
            性别:
        </p>
        <p>
            <input type="radio" th:checked='${user.gender=="0"}'/> 男
        </p>
        <p>
            <input type="radio" th:checked='${user.gender=="1"}'/> 女
        </p>
        <p>
            班级
        </p>
        <p>
            <select name="" id="">
                <option value="1" th:selected="${user.classroomId==1}">1班</option>
                <option value="2" th:selected="${user.classroomId==2}">2班</option>
                <option value="3" th:selected="${user.classroomId==3}">3班</option>
            </select>
        </p>

    </form>
</body>
</html>
```
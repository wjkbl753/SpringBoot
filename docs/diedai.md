```html
 <table border="1" cellspacing="0">
    <tr>
        <td>序号</td>
        <td>用户名</td>
        <td>性别</td>
        <td>邮箱</td>
        <td>班级</td>
    </tr>
    <tr th:each="user,i:${userList}">
        <td th:text="${i.count}">序号</td>
        <td th:text="${user.userName}">用户名</td>
        <td th:if='${user.gender=="0"}'>男</td> <td th:if='${user.gender!="0"}'>女</td>
        <td th:text="${user.email}">邮箱</td>
        <td th:text="${user.classroomId}">班级</td>
    </tr>
</table>
```
## if
```html
性别：<span th:if='${user.gender="0"}'>男</span>
     <span th:if='${user.gender!="0"}'>女</span>
```

## switch-case
```html
班级:
<span th:switch="${user.classroomId}">
    <span th:case="1">1</span>
    <span th:case="2">2</span>
    <span th:case="3">3</span>
</span>
```

!> 上面的值是区分字符串和数字的

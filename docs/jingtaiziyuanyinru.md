```html
<!-- 绝对路径以static开始 -->
 <link th:href="@{/css/bootstrap.min.css}" rel="stylesheet">
 <script th:src="@{/js/jquery.min.js}"></script>
```

## 资源包含

### 在template文件夹创建被资源文件common.html
```html
<!DOCTYPE html>
<html lang="en" xmlns:th="http://www.thymeleaf.org">
<th:block th:fragment="head">
    <link th:href="@{/css/bootstrap.min.css}" rel="stylesheet">
    <link th:href="@{/css/font-awesome.min.css}" rel="stylesheet">
    <link th:href="@{/css/animate.css}" rel="stylesheet">
    <link th:href="@{/css/style.css}" rel="stylesheet">
</th:block>
<th:block th:fragment="foot">
    <script th:src="@{/js/jquery.min.js}"></script>
    <script th:src="@{/js/bootstrap.min.js}"></script>
    <script th:src="@{/js/plugins/metisMenu/jquery.metisMenu.js}"></script>
    <script th:src="@{/js/plugins/slimscroll/jquery.slimscroll.min.js}"></script>
    <script th:src="@{/js/plugins/layer/layer.min.js}"></script>
    <!-- 自定义js -->
    <script th:src="@{/js/hplus.js}"></script>
    <script type="text/javascript" th:src="@{/js/contabs.js}"></script>
    <!-- 第三方插件 -->
    <script th:src="@{/js/plugins/pace/pace.min.js}"></script>
</th:block>
</html>
```

### 其他页面引入此资源文件
```html
 <div th:replace="/common::head"/>
 <!-- 或 -->
 <div th:replace="common::foot"/>
```
# 入门django

startproject #创建项目

startapp #创建应用

runserver#本地简易运行

shell #进入python-shell环境

test#用例测试



makemigrations#创建模型变更的迁移文件

migrate  #执行上一个命令创建的迁移文件

dumpdata # 把数据库数据导出到文件

loaddata # 文件数据导入到数据库

## 项目目录文件

setting配置

 urls 路由

**wsgi** Web服务器网关接口（Python Web Server Gateway Interface，缩写为*WSGI*）是为Python语言定义的Web服务器和Web应用程序或框架之间的一种简单而通用的接口

manage 管理

## 应用 vs 项目

项目基于应用，项目包含一组配置和若干个应用，可直接运行，而应用只是一个可重用的python软件包，每个应用可以自己管理模型、视图、模板、路由和静态文件等

## 应用目录文件

views 视图处理的地方

models 应用模型

admin Admin模块管理对象的地方

apps 声明应用的地方

tests 编写应用测试用例的地方

urls（自创）管理应用路由的地方

## 视图：函数产生内容

## 路由：绑定视图函数和url

## 过程：

![过程](https://github.com/Ccxcui/DjangoStudy/blob/master/django%E8%BF%87%E7%A8%8B.jpg)

## 模型层

what：位于视图层与数据库之间；对象和数据库表之间转换；

why：屏蔽不同数据库之间的差异；提供很多便捷工具有助于开发

where：setting database

## Django shell

临时性操作 小范围的debug save

## Django Admin

后台管理工具  

步骤： 

python manage.py createsuperuser

python manage.py runserver

浏览器 localhost:8080/admin

要注册模型才能使用：admin.py 

```python
form .models import xxx

admin.site.register(xxx)
```

注意可在模型中自定义函数返回每个item的id等，如：models.py

```python
def __str__(self):
    return self.title
```

##  Django的模板系统

原因：网页逻辑和网页视图应该分开

简介：表现形式是文本

基本语法：

{{ 变量 }}

{% for x in list %}...{% endfor %}

{% if %}...{% else %}...{% endif %}

# Django项目开发流程
##一.前期准备
> ##### 开发环境
    1.某个版本Django(Django==2.2.6)
    2.虚拟环境Virtualenv
    3.python(建议python3)
    4.mysql(本地测试开发时可暂不用)
--------

## 二.Django常用命令
>##### 创建Django项目
    django-admin.py startproject "项目名"
>##### 创建Django应用
    python manage.py startapp "应用名"
>##### 启动开发网站
    python manage.py runserver 指定ip:指定端口
    例如：python manage.py runserver 127.0.0.1:8001
>##### 数据迁移操作
    python manage.py makemigrations
    python manage.py migrate
>##### 创建超级管理员
    python manage.py createsuperuser
>##### 进入shell界面调试
    python manage.py shell
-----

## 三.虚拟环境常用命令(建议在虚拟环境下开发，保证开发环境与生产环境的一致性)
>#####创建虚拟环境
    virtualenv --python=python3 虚拟环境名
>#####启用虚拟环境
    source 虚拟环境名/bin/activate
>#####虚拟环境python第三方库一键导出与安装
    pip freeze > requirements.txt
    pip install -r requirements.txt
>#####退出虚拟环境
    deactivate(在虚拟环境目录下执行)
------

## 四.Django项目组成
>#####项目配置文件(项目同名文件夹)
    __init__.py: 配置数据库时，须在此文件内引入数据库相关的第三方库
    setting.py: 配置数据库;配置static与template等相关路径;注册app
    urls.py: 根路由，可include各app子路由
    view.py: 根页面的视图函数
    wsgi.py: 用于项目部署
    
>#####APP
    应用文件，同一项目可以扩展多个APP
>#####静态文件(static)
    js，css文件，可引入第三方框架(jQuery,bootstraps,echart等)
>#####模板文件(template)
    HTML文件，用于页面展示
>#####manage.py
    命令行文件，具体用法见<二>
>#####数据库文件
    Django默认为db.sqlite3，若项目配置文件中未配置相关数据库，则该文件在数据迁移后生成
----


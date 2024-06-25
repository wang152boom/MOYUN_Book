# Moyun Book Sharing Session

> “墨韵”读书分享会项目，2024spring软件工程大作业。

## Contributors
按顺序依次为：王雨桐，钟昊洋，席灏铖，谢媛，张文桥，李佳荃
<a href="https://github.com/wang152boom" alt="wang152boom"><img src="https://avatars.githubusercontent.com/u/167402892?v=4" style="width: 64px; height: 64px;"/></a>
<a href="https://github.com/FlashBlank7" alt="FlashBlank7"><img src="https://avatars.githubusercontent.com/u/122159986?v=4" style="width: 64px; height: 64px;"/></a>
<a href="https://github.com/SpikeShaun" alt="SpikeShaun"><img src="https://avatars.githubusercontent.com/u/121989821?v=4" style="width: 64px; height: 64px;"/></a>
<a href="https://github.com/Flora-xyyy" alt="Flora-xyyy"><img src="https://avatars.githubusercontent.com/u/121485747?v=4" style="width: 64px; height: 64px;"/></a>
<a href="https://github.com/KidZwq" alt="KidZwq"><img src="https://avatars.githubusercontent.com/u/128034889?v=4" style="width: 64px; height: 64px;"/></a>
<a href="https://github.com/LiJiaquan1" alt="LiJiaquan1"><img src="https://avatars.githubusercontent.com/u/167403951?v=4" style="width: 64px; height: 64px;"/></a>

## 基本功能

* 账号管理：注册、登录、登出、找回密码(需要配置邮箱服务)、修改个人信息、查看他人信息
* 书评：写书评、书评点赞、书评回复、书评搜索
* 书籍：书籍搜索、书籍详情
* 圈子：创建圈子、查看圈子详情、修改圈子信息(仅限管理员)
  * 帖子：发表新帖、回帖

### 特色功能

* 自定义Error页面
* 消息中心：整合书评回复、圈子新帖、帖子回复、私信等消息

  
### 运行环境

> 该项目在`Windows 10`上测试通过，软件版本如下:

* Python 3.11.3
* Flask 2.0.2
* MySQL 8.0.30

## 注意事项

* 部署路径请全英文，但数据库中的内容允许中文、其他语言甚至Unicode表情。

## 运行方式
* 运行app.py的主函数即可


## 文件结构

> 为便于继续开发，我们团队特此说明项目的文件结构。

```ini
├───documents # 两份无关痛痒的文档，分别记录了部分变量名和界面类的设计
├───Service # 服务层，封装了数据库操作和文件操作的业务逻辑，供控制层调用，类似于MVC中的Model
│   ├───DB
│   │   ├───ExtractInfo.py # 与数据库的表相对应，负责将数据模型转换为字典
│   │   └───Operation.py # 数据库部分的核心，只有一个class Database，声明了数据库中所有表的数据模型，以及部分数据库操作，封装了数据库相关的业务逻辑，供其他模块调用
│   └───File
│       └───File.py # 与文件相关的操作，主要用于寻找文件，返回文件路径
├───static # 静态资源，用于存储多媒体文件和网页上的部分资源
│   ├───assets # 网页模板的静态资源
│   │   ├───home # 除根页面外的其他页面的相关资源
│   │   │   ├───css
│   │   │   ├───js
│   │   │   ├───sass
│   │   │   │   ├───base
│   │   │   │   ├───components
│   │   │   │   ├───layout
│   │   │   │   └───libs
│   │   │   └───webfonts
│   │   └───index # 登录前界面(根页面)的相关资源，即 127.0.0.1:5000 页面所需的资源
│   │       ├───css
│   │       ├───js
│   │       ├───sass
│   │       │   ├───base
│   │       │   ├───components
│   │       │   ├───layout
│   │       │   └───libs
│   │       └───webfonts
│   ├───bookCover # 存放书籍的封面图
│   ├───errorImage # 存放错误页面的图片
│   ├───groupIcon # 存放圈子的图标
│   ├───images
│   │   └───index # 登录前界面(根页面)的一些图片
│   ├───journalHeader # 书评的封面图(头图)
│   ├───logo # 网站的logo
│   └───profilePhoto # 用户头像
├───templates # 不同网页的HTML模板，模板名称基本与网页的URL相对应，类似于MVC中的View
├───app.py # 声明了整个网站项目的路由逻辑，类似于MVC中的Controller，同时项目也是从这个文件启动的
├───config.yaml # 配置文件，存放了数据库的连接信息、邮箱的配置信息、API的key等
├───DDL.sql # 数据库的声明文件，用于初始化数据库
└───init_db.py # 初始化数据库的脚本，用于创建数据库、数据库的管理员账户、网站的1号用户(管理员)
```


## Reference

### 资源来源

* HTML模板
  * [Future Imperfect | HTML5 UP](https://html5up.net/future-imperfect)
* Logo设计：[AIDesign](https://ailogo.qq.com/guide/brandname)

### 参考资料

* [欢迎来到 Flask 的世界 — Flask中文文档(2.1.x)](https://dormousehole.readthedocs.io/en/latest/index.html)
* [Flask 教程_w3cschool](https://www.w3cschool.cn/flask/)
* [CSS：层叠样式表 | MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS)
* [HTTP 响应状态码 - HTTP | MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Status)
* [AJAX | 菜鸟教程](https://www.runoob.com/ajax/ajax-tutorial.html)

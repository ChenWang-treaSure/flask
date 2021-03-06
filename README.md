<h1>使用说明</h1>
  <h2>1 环境介绍</h2>
<h4>1.1 python环境</h4>
python3.8.6 (64 bit)
<h4>1.2 开发环境</h4>
PyCharm Professional<br>
version:2020.2.1
<h4>1.3 主要外部依赖包为：</h4>
Flask 1.1.2<br>
Flask_Bootstrap 3.3.7<br>
Flask-Login 0.5.0<br>
Flask-SQLAlchemy 2.4.4<br>
Flask-Script 2.0.6<br>
Flask-WTF 0.14.3<br>
WTForms 2.3.3<br>
PyMySQL 0.10.1<br>
xlrd 1.2.0
<h4>1.4 服务器</h4>
服务器使用的是阿里云的ESC云服务器<br>
OS：ubuntu0.16.04.1<br>
<h4>1.5 数据库</h4>
数据库使用的是ESC服务器上的mysql<br>
版本：5.7.30
<h2>2 项目结构</h2>
<h4>2.1 文件介绍</h4>
├── app //项目主目录<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── auth //登录模块<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── __init__.py //初始化文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── forms.py //表单文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── views.py //路由文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── sysadmin //系统管理员模块<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── __init__.py //初始化文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── forms.py //表单文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── views.py //路由文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── eduadmin //教务管理员模块<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── __init__.py //初始化文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── forms.py //表单文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── views.py //路由文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── student //学生模块<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── __init__.py //初始化文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── forms.py //表单文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── views.py //路由文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── teacher //教师模块<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── __init__.py //初始化文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── forms.py //表单文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── views.py //路由文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── static //静态文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── css //样式文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── nav.css //登录模块<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── JS //JS文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── sysadmin.js //系统管理员JS<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── eduadmin.js //教务管理员JS<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── student.js //学生JS<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── teacher.js //教师JS<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── uploads //Excel文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── templates //模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── includes //引用文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── _navbar.html //功能栏模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── base.html //基模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── changepwd.html //修改密码模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── eduadmin.html //教务员模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── index.html //初始界面模板（无用，删除会报错？）<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── login.html //登录模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── student.html //学生模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── sysadmin.html //系统管理员模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── teacher.html //教师模板<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;├── __init__.py //初始化文件<br>
│&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;└── models.py //SQLAlchemy模型<br>
├── manager.py //程序入口<br>
└── README.md //MarkDown文件
<h4>2.2 模型介绍</h4>
Flask-Blueprint(蓝图)<br>
分别为四个角色以及登录功能共五个模块注册蓝图<br>
static&&templates文件抽离，单独存放<br>
程序入口抽离，与app同级<br>
<h2>3 系统介绍</h2>
<h4>3.1 主要角色</h4>
本系统为教务管理系统，用户主要分：<br>
(1)系统管理员<br>
(2)教务管理员<br>
(3)教师<br>
(4)学生<br>
<h4>3.2 主要功能</h4>
系统管理员主要功能有：<br>
（1）教务管理员维护<br>
（2）系所信息维护<br>
（3）专业信息维护<br>
（4）班级信息维护<br>
（5）课程类别维护<br>
（6）系统管理员登录密码修改功能<br>
教务员的主要功能有：<br>
（1）教务管理员个人登录密码修改功能<br>
（2）教师信息维护<br>
（3）学生信息维护<br>
（4）课程基本信息维护<br>
（5）排课计划数据维护<br>
教师主要功能有：<br>
（1）教师个人登录密码修改功能<br>
（2）教师开课信息查看<br>
（3）成绩录入功能<br>
（4）成绩导入功能<br>
学生主要功能有：<br>
（1）学生个人登录密码修改功能<br>
（2）基本信息查看<br>
（3）学生选课（批操作）<br>
（4）学生退课功能（批操作）<br>
（5）学生成绩查询<br>
<h2>4 运行说明</h2>
<h4>4.1 方法一</h4>
打开python Terminal输入python manager.py dev(livereload模式)
<h4>4.2 方法二</h4>
打开python Terminal输入python manager.py

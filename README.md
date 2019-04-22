# 旅游意向调查
这是一个通过浏览本网页的人进行投票选取想去的旅行的5个城市。是一个简单的项目，也是我的作业，Bug很多，欢迎各位大佬交流。

# 摘要
简单的介绍一下，本项目是用Python3和flask框架来写的。整个项目结构暂时比较简单，实现的功能也不多。
主要的功能，通过浏览的用户进行投票，在所给的城市选项中选择出用户比较有旅游意向的城市，我们会将数据存储到数据库中，根据总共记录的投票结果，我们给出前十人气最高的城市，作为推荐城市给用户浏览。顶部热门城市中我加了几个城市的宣传片链接供用户跳转。大致功能就这些。


# 目录
- main_web.py 这是主要的文件，整个web程序就是运行这个文件
- sqite_date.py  这是用于生成数据库的文件，我之所以没有用flask的数据库扩展，是在使用Flask数据库扩展时出现了一些问题，所以我采用这样的方式用数据库
- welcome.txt  这是网站首页做简要介绍时的说明字段
- templates  这个文件夹里存放了所有的网页界面布局

# 食用本项目说明（以下说明基于liunx)
### 一：建议在虚拟环境中下载，毕竟是web服务，将环境独立出来很有必要
##### 终端进入做为虚拟环境的文件夹下，开始建立虚拟环境：
-     python3 -m venv vm
##### 启动虚拟环境
-     source vm/bin/activate
##### 建立一个文件夹存储本项目文件
-     mkdir app
-     cd app
##### 通过git方法下载本项目
-     git clone https://github.com/byack/TravelDate--Python-flask.git

### 二：在虚拟环境中安装本项目所需要的包
##### flask框架
-   pip3 install flask
##### 安装flask-bootstrap用于渲染网页
-   pip3 install flask-bootstrap
##### 安装flask-WTF来制作表单
-   pip3 install flask-WTF
            
### 三：启动服务(启动虚拟环境并进入到下载的文件夹中）
##### 第一次启动，在没有travel_date.db这个数据库的情况下,运行数据库文件创建一个数据库（有数据库可以跳过这一步）
-   python3 sqite_date.py
##### 运行网站
-   python3 main_web.py
            
# 常见问题
数据只用于存储数据，每一次启动这个web服务，程序会先将数据库中已有的投票数据遍历一次，统计已有的投票数据，之后的每一次投票，边存入数据库，投票数据边加入到程序的字典当中。当数据库中的数据量很大后，启动web服务应该会需要很多时间，启动完成后会好很多。
    
# 可忽略部分
本人学生一枚，这只是我的一个作业，其中还存在许多问题，望大佬指点。希望对你有一丢丢帮助

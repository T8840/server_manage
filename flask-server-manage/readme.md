# ServerManagement  

服务器管理工具，目前有文件管理器、进程监控、计划任务、webSSH、多主机管理、本地桌面、内网穿透等，后续会加入更多运维相关，本项目后端python+flask<br>

## 功能介绍
### 1.文件管理
兼容windows和linxu的文件管理器,目前有文件的批量压缩、下载、重命名、文件内容在线编辑等. <br>
文件管理器中进行下载时,若下载的是文件,将会直接下载,若为目录,则会压缩为zip后下载 <br>
文件后缀为`.zip`,`.gz`,`.tar`的,可以在线解压 <br>
可对文件进行分享,提供一个类似简易网盘的功能 <br>
并提供一个批量文件操作的按钮,支持跨文件夹操作,后续可能会加入更多功能 <br>

### 2.进程监控
显示CPU、内存、磁盘状态,并实时显示网速 <br>
同时显示了进程以及网络进程,点击进程名可以查看进程详细信息 <br>

### 3.计划任务
可以设定以秒为单位的循环执行,也可以设定规则,如每周三的12:50:30,每月的23号15:30:00 <br>

### 4.shell
一个是个比较low的webSSH,最近可能没时间去完善这一块<br>
还有一个是多主机批量执行shell,支持root身份运行(目前很简陋,后续会添加更多功能)<br>

### 5.资源监控
本质上就是一个定时储存服务器资源使用情况的定时任务，前端请求到储存的数据后解析，最后用echarts生成折线图，为了尽量少的占用服务器资源，解析操作都是在网页前端进行的。<br>

### 6.便捷操作
现在只有一个快捷按钮的功能,就是可以自行设定一个常用的shll,方便快速调用,执行前可以做出修改,未来会加入其他我的脑洞...<br>

### 7.本地桌面
此功能仅限windows可用

### 8.内网穿透
选用功能,将项目下server.zip解压并在有外网IP的服务器上运行,在本地服务器管理工具运行时修改配置（外网服务器需要开启80端口，10000-20000端口，其中80端口为综合管理平台，可以查看所有的连接设备，可以查看其绑定的外网IP+端口，10000-20000端口为内网穿透的绑定端口）,即可实现内网穿透,在有外网IP的服务端上一键查看所有连接设备,后续会加入查看所有服务器实时状态等功能

### 9.软件管理
仅在LINUX可用,以添加nginx一键安装配置(支持ubuntu及centos,使用ubuntu的同学使用之前记得更新apt源,推荐使用中科大apt源)

## 使用说明
### 运行本项目需要自行pip安装`flask`,`chardet`,`datetime`, `paramiko`,`pillow`,`psutil`,`pyautogui` <br>
### 或在目录下 python3 -m pip -r install requirements.txt<br>
以Ubuntu为例：
先安装python环境<br>
`apt install python3`<br>
`apt install python3-pip`<br>
然后安装依赖库<br>
`python3 -m pip install flask paramiko pillow datetime chardet pautil `<br>
最后进入项目运行就行了<br>
`python3 index.py`<br>
如果你是windows，记得还需要pip install pyautogui
## 本项目后端给前端传值全部使用json,前端用jq处理、发送请求并生成最终页面<br>
## 其中的文件管理器部分前端给后端传值,大部分采用base64编码 <br>

## 使用前切记修改config/config<br>
相关操作：
```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python index.py
pip uninstall  Flask Jinja2
pip install Flask Jinja2
python index.py
pip install six
python index.py
```

浏览器打开：IP:9001
账户密码在config/config.py中可以看到
 

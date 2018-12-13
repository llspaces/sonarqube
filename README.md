# SonarQube安装配置
1.	系统环境
centos7
2.	SonarQube版本
sonarqube-7.4.zip(https://www.sonarqube.org/downloads/) <br/>
sonar-l10n-zh-plugin-1.24.jar(https://github.com/SonarQubeCommunity/sonar-l10n-zh/releases)
3.	安装配置
(1). 将安装包和汉化包上传至服务器<br/>
(2). 解压，授权（elasticsearch需要非root用户启动）<br/>
   unzip sonarqube-7.4.zip<br/>
   cp -r sonarqube-7.4 /usr/local<br/>
   chown -hR hadoop:hadoop sonarqube-7.4(hadoop:hadoop以你服务器上非root用户名称而定)<br/>
   ll (检查权限)<br/>
(3). 安装mysql(需要5.6以上版本，相关步骤略)<br/>
(4). 安装jdk，配置环境变量(相关步骤略)<br/>
(5). 修改配置文件（elasticsearch暂时用目录下自带的）<br/>
   cd sonarqube-7.4/conf/<br/>
   两个核心配置文件  <br/>
   添加jdk配置<br/>
4.	启动测试
  ./bin/linux-x86-64/sonar.sh start(stop | restart …)<br/>
  第一次启动会初始化数据库所以会比较慢，日志默认在logs/下<br/>
  tail -f web.log<br/>
  等待启动成功<br/>
 
5.	尝试使用
打开浏览器访问http://192.168.4.244:9000/<br/>
默认用户名密码是admin/admin<br/>
首次登录按照提示初始化一个token,方便后续编辑器使用<br/>
 
6.	SonarQube插件
Eclipse 打开Help > Install New Software... ，输入下面这个网址 http://downloads.sonarsource.com/eclipse/eclipse/<br/>
Idea 直接plugins中安装即可sonarlint

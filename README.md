# 学习RESTful web service记录
## 看文档  
* 用时约1.5小时 [官网地址](https://spring.io/guides/gs/rest-service/)
## 写代码-用时约1小时
* github操作 
  + 创建仓库learn-restful
  + 编辑readme
  + 创建dev分支
* 本地操作
  + git clone 远程仓库
  + git 创建分支dev
  + 与远程仓库dev分支关联 
    - git branch --set-upstream-to=origin/<branch> dev
  + 拉取远程仓库初始文件 git pull
  + vscode 打开文件夹
  + 添加pom.xml，并按照官网教程添加内容
  + 添加src/main/java/hello目录
  + 添加Greeting.java,GreetingController.java,Application.java
  + 本地learn-restful目录下执行mvn spring-boot:run, 启动服务
  + 浏览器访问http://localhost:8080/greeting?name=liqian
    - 响应结果：{"id":1,"content":"Hello, liqian!"}
  + 浏览器访问http://localhost:8080/greeting
    - 响应结果：{"id":2,"content":"Hello, World!"}

# 学习RESTful web service记录
## 看文档  
* 用时约1.5小时 [官网地址](https://spring.io/guides/gs/rest-service/)
## 写代码并运行-用时约2小时
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
  + 本地git提交代码
  + 本地代码提交到github 
    - git push origin dev
## 总结
* A key difference between a traditional MVC controller and the RESTful web service controller above is the way that the HTTP response body is created. Rather than relying on a view technology to perform server-side rendering of the greeting data to HTML, this RESTful web service controller simply populates and returns a Greeting object. The object data will be written directly to the HTTP response as JSON.  
  + 传统MVC controller RESTful web service controller之间的一个关键区别是HTTP响应体的创建方式。RESTful web service controller并不依赖视图技术来将greeting呈现到HTML，而是简单地填充并返回一个greeting对象。对象数据将直接以JSON的形式写入HTTP响应。
* This code uses Spring 4’s new @RestController annotation, which marks the class as a controller where every method returns a domain object instead of a view. It’s shorthand for @Controller and @ResponseBody rolled together.  
  + controller代码中使用了spring 4的一个新的注解@RestController,这个注解标识一个controller类每个方法都返回一个领域对象而不是视图,就相当于@Controller与@ResponseBody的缩写
* The Greeting object must be converted to JSON. Thanks to Spring’s HTTP message converter support, you don’t need to do this conversion manually. Because Jackson 2 is on the classpath, Spring’s MappingJackson2HttpMessageConverter is automatically chosen to convert the Greeting instance to JSON.  
  + springmvc框架会自动将controller方法返回的greeting对象转为json,不需要手动处理,这依赖于spring的MappingJackson2HttpMessageConverter
* @RequestParam binds the value of the query string parameter name into the name parameter of the greeting() method. If the name parameter is absent in the request, the defaultValue of "World" is used.  
  + @RequestParam注解可以将请求地址中的参数绑定到方法的参数上

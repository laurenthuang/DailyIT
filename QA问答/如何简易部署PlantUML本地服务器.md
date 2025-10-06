# Q: 如何简易部署PlantUML本地服务器？

```shell
start /B java -jar plantuml.jar -picoweb:<port>:127.0.0.1:stop
```

在IP地址后加`stop`参数的作用：
在运行时，可以通过浏览器访问地址`http://127:0.0.1:<port>/plantuml/stopserver`来终止服务器

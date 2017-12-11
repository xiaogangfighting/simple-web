结构：maven + 内嵌jetty
构建：
1、maven archetype插件，simple-webapp
2、在src/main/webapp下添加资源+index.html
3、在src/main/webapp/WEB-INF下，修改web.xml
4、配置pox.xml中的jetty Plugin，添加：
<configuration>
	<httpConnector>
		<port>9090</port>
		<host>localhost</host>
	</httpConnector>
	<scanIntervalSeconds>1</scanIntervalSeconds>
</configuration>

调试测试：
mvn jetty:run

部署：
1、服务器上安装maven，有mvn命令；
2、修改pox.xml文件中的地址，改为服务器IP
3、mvn jetty:run
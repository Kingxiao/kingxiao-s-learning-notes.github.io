# mysql5.7无法连接mysql workbench
	
始终报错：Access denied for user 'root'@'localhost'
系统配置：ubuntu18.04
原因：5.7与其不兼容，需要mysql8.0版本
* [ ] 解决方案：卸载
	* dpkg --list|grep mysql #查看所有依赖
	* sudo apt-get remove mysql-common#卸载所有mysql comman
	* sudo apt remove #自动删除
	* dpkg --list|grep mysql#查看卸载残余
	* dpkg -l |grep ^rc|awk '{print $2}' |sudo xargs dpkg -P#清除剩余数据
* [ ] 安装mysql8.0
	* 下载地址：https://dev.mysql.com/downloads/repo/apt/
	* cd Downloads/#进入下载文件夹
	* sudo dpkg -i mysql-apt-config_0.8.10-1_all.deb#安装
	* 弹出界面选择 “Mysql Server & Cluster”
	* 选择mysql8.0，自动返回上一页，tab选择ok，配置完成
	* sudo apt update#更新系统
	* sudo apt install mysql-client mysql-server mysql-workbench#安装mysqlGUI工具workbench
	* 选择y，依次安装
	* 输入两次mysql 的root密码
	* 出现软件包描述页面，enter确认，进入加密方式选择界面
	* 选择非推荐的那个，即Use Legacy Authentication Method
	* 安装完成
  
[参考1](https://blog.csdn.net/w3045872817/article/details/77334886)

[参考2](https://kuaibao.qq.com/s/20180708A0MRNY00?refer=spider)

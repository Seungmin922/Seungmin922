# Ubantu系统minecraft开服

**Made by : Seungmin922**

## 1. 安装前置
当前用户身份查询
```
whoami
```

软件包更新
```
sudo apt update
```

安装MCDReforged（简称为 MCDR，下同）
 查看Python编程版本的信息
```
python3 –version
```

下载Python编程
```
sudo apt install python3
```

安装java 21
```
sudo apt install openjdk-21-jdk

java -version  #该命令用于查询java版本以确定Java     是否安装成功
```

安装screen终端多路复用器
```
sudo apt install screen

screen -version  #该命令用于查询screen版本以确定screen是否安装成功
```

安装解压缩软件
```
sudo apt install zip unzip
```

安装网络下载器
```
sudo apt install wget
```

安装MCDR
```
pip3 install mcdreforged
```

对于国内用户，你可以在 pip 指令的末尾添加 -i https://pypi.tuna.tsinghua.edu.cn/simple 后缀来使用 清华 pypi 镜像 来加速 MCDR 的下载安装：
```
pip3 install mcdreforged -i https://pypi.tuna.tsinghua.edu.cn/simple
```

假设你想在 my_mcdr_server 这一个文件夹中运行 MCDR，那么你可以运行以下指令以初始化 MCDR 的运行环境
```
cd my_mcdr_server
mcdreforged init
```

MCDR 将生成默认的配置文件、权限文件，以及一些默认的文件夹。此时的路径结构将会如下所示：
```
my_mcdr_server/
 ├─ config/
 ├─ logs/
 │   └─ MCDR.log
 ├─ plugins/
 ├─ server/
 ├─ config.yml
 └─ permission.yml
```

## 2. 启动MCDR
MCDR启动
```
python3 -m mcdreforged
```

输出示例：
```
MCDReforged 2.x.x is starting up
MCDReforged is open source, u can find it here: https://github.com/MCDReforged/MCDReforged
[MCDR] [13:05:59] [MainThread/INFO]: Language is set to en_us
[MCDR] [13:05:59] [MainThread/INFO]: Encoding / Decoding method is set to utf8 / utf8
[MCDR] [13:05:59] [MainThread/INFO]: Plugin directory list:
[MCDR] [13:05:59] [MainThread/INFO]: - plugins
[MCDR] [13:05:59] [MainThread/INFO]: Handler has set to vanilla_handler
[MCDR] [13:05:59] [MainThread/INFO]: MCDReforged is running on Python 3.11.9 environment
[MCDR] [13:05:59] [TaskExecutor/INFO]: Refreshing all plugins
[MCDR] [13:05:59] [TaskExecutor/INFO]: No plugin has changed; Active plugin amount: 2
[MCDR] [13:05:59] [MainThread/INFO]: Starting the server with command "echo Hello world from MCDReforged"
[MCDR] [13:05:59] [MainThread/INFO]: Server is running at PID 10
[Server] Hello world from MCDReforged
[MCDR] [13:05:59] [MainThread/INFO]: Server process stopped with code 0
[MCDR] [13:05:59] [MainThread/INFO]: Server stopped
[MCDR] [13:05:59] [MainThread/INFO]: Stopping MCDR
[MCDR] [13:05:59] [MainThread/INFO]: Stopping advanced console
[MCDR] [13:05:59] [MainThread/INFO]: bye
```

更改MCDR启动参数
```
start_command: echo Hello world from MCDReforged
#"echo Hello world from MCDReforged" 写成你服务器的启动参数或者启动脚本
```



screen后台窗口使用
```
screen -S <session-name>
#创建一个名为<session-name>的会话

screen -ls
#罗列出所有会话

screen -r <session-name>
#进入一个名为<session-name>的会话
```

ufw防火墙（大可不必）
```
sudo apt install ufw  #安装防火墙ufw

sudo ufw status verbose  #查看防火墙状态

sudo ufw allow 2222/tcp  #允许特定端口访问（例如  端口222）
```

解压缩zip文件
```
unzip <filename>  
#解压名为<filename>的文件

zip -r <filename.zip> <filename>
#将名为<filename>的文件压缩为名为<filename.zip>的文件
```

文件目录操作
```
cd /home
#前往home文件夹下

cd ./server
#前往上个文件夹的server文件夹下

ls
#查看当前文件夹内内容
```

给予755权限
```
chmod 755 <start.sh>
#给予名为<start.sh>的文件755权限
```

启动服务器
```
java -Xmx1G -jar <server.jar> nogui
#用java启动<server.jar>并给予该文件最大1g运行内存
```

启动服务器（通过运行文件实现）
```
./start.sh
```


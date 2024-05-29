embupdated 后台程序，监听升级指令后开始升级
embupdatec 升级工具，可以制作升级包，发送升级包等
libembupdate 工具库

用法:
```bash
embupdated [<-l|--log-level> ERROR | DEBUG | VERBOSE] <-f|--file> logfile [<-b|--board> board_type] [<-p|--port> port]
```


```bash
embupdatec <-v|--version>
```


```bash
embupdatec <-r|--root> path  [<-o|--output> packName] <-s|--source> srcs|dirs... [ <-e|--encrypt> algorithm...] [<-b|--board> board_type] [<-c|--compress-level> 0~9]
```
        如果不指定名称则生成默认名称

```bash
embupdatec <-f|--file> packName <-a|--append> srcs|dirs... <-r|-root> path
```

```bash
embupdatec <-f|--file> packName  <-t|--transmit> files_store_ips [<-p|--port> port]
```


files store ips格式:json格式的数组，存放要升级的板子的ip
```
[
"192.168.2.165",
"192.168.2.166",
"192.168.2.167"
]
```


```bash
embupdatec <-f|--file> packName <-tp|--transport> ips... [<-p|--port> port]
```

要点：
        构建项目是可以选择是否使用加密(加密的话程序大小会变大）
        先压缩，再加密


功能：
	1. 制作升级包,支持追加内容到升级包
	2. 多设备升级，支持从文件中读取指定设备ip，端口号,#可注释
	3. 单设备返回shell命令执行结果，支持脚本
	4. 多设备重启
	5. 支持多设备直接传文件(先压缩，再传输）
	6. 支持传输过程加密

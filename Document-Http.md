# AutoServer Http 接口文档


### 开始

首先，下载apk(https://github.com/MarsDiplomatToEarth/AutoServerCN),
在你的安卓设备安装并运行(可以后台操作)，它将会在你的移动设备端开启一个服务器监听你的http请求，通过这些请求你可以实现自动点击，滑动，获取手机信息，录音，录屏等等操作，它封装了大量自动化操作。可以适应不同的编程语言。是uiautomatorviewer和脚本精灵的高级在线版。
接下来将为你介绍http接口。

### Shell接口

------------

- 检测你的安卓设备是否Root，如果已root，将返回True，否则返回False
```xml
  http://{your device ip:port}/root
  (比如 http://192.168.1.100:8080/root)
```

-返回你的安卓设备的分辨率
```xml
  http://{your device ip:port}/size

  (比如http://192.168.1.100:8080/size)
```

- 执行Shell命令(拥有Root权限)，并返回结果
```xml
  http://{your device ip:port}/shell?cmd={你的Shell命令}

  (比如http://192.168.1.100:8080/shell?cmd=echo autoserver)
```
```xml
   返回的格式:
   
  "s:"+successMsg+" m:"+errorMsg+" r:"+result

  (successMsg 是真正执行Shell返回的结果)
```

- 执行Shell命令(没有有Root权限)，并返回结果
```xml
  http://{your device ip:port}/shellnotroot?cmd={your command}

  (such as http://192.168.1.100:8080/shellnotroot?cmd=echo autoserver)
```

------------

### 截图接口 (Request Root Permission)

- 截取设备图片并返回图片
```xml
  http://{your device ip:port}/jpg
  
  http://{your device ip:port}/png

  (比如http://192.168.1.100:8080/jpg)
```

------------

### Xml接口(Request Root Permission)

- 返回你设备当前屏幕的xml, 它会返回 screen.xml 或者 screen.uix
```xml
  http://{your device ip:port}/uix
  
  http://{your device ip:port}/ui

  (such as http://192.168.1.100:8080/ui)
```

------------

### Xml选择器(帮助你通过xml控件找到坐标)
- 通过你提供的节点类型和节点值返回json列表格式的xml节点(节点值包含就返回)
```xml
  http://{your device ip:port}/getnodelistbykeyvaluecontains?key={your key}&value={your value}

  (such as http://{your device ip:port}/getnodelistbykeyvaluecontains?key=text&value=Start Server)
```
```xml
   返回格式:
   
   json列表格式
  
   (json列表格式包括节点所有的信息)
```

- 通过你提供的节点类型和节点值返回json列表格式的xml节点(节点值相等才返回)
```xml
  http://{your device ip:port}/getnodelistbykeyvalue?key={your key}&value={your value}

  (such as http://{your device ip:port}/getnodelistbykeyvaluecontains?key=text&value=Start Server)
```
```xml
   返回格式:
   
   json列表格式
  
   (json列表格式包括节点所有的信息)
```

- 通过你提供的节点类型和节点值返回列表格式的坐标(节点值包含就返回)
```xml
  http://{your device ip:port}/getboundsbykeyvaluecontains?key={your key}&value={your value}

  (such as http://{your device ip:port}/getboundsbykeyvaluecontains?key=text&value=Start Server)
```
```xml
   返回格式:
   
   坐标列表
```

- return Bounds List of the real time xml with your key and value(equal).
```xml
  http://{your device ip:port}/getboundsbykeyvalue?key={your key}&value={your value}

  (such as http://{your device ip:port}/getboundsbykeyvalue?key=text&value=Start Server)
```
```xml
   Return Format:
   
   Bounds(String) List
```

- return the first of Node List of the real time xml with your key and value(equal).
```xml
  http://{your device ip:port}/getnodebykeyvalue?key={your key}&value={your value}

  (such as http://{your device ip:port}/getnodebykeyvalue?key=text&value=Start Server)
```
```xml
   Return Format:
   
   the first of Node List
```
- return the first of Node List of the real time xml with your key and value(contains).
```xml
  http://{your device ip:port}/getnodebykeyvaluecontains?key={your key}&value={your value}

  (such as http://{your device ip:port}/getnodebykeyvaluecontains?key=text&value=Start Server)
```
```xml
   Return Format:
   
   the first of Node List
```
- return the first bounds of Node List of the real time xml with your key and value(contains).
```xml
  http://{your device ip:port}/getboundbykeyvaluecontains?key={your key}&value={your value}

  (such as http://{your device ip:port}/getboundbykeyvaluecontains?key=text&value=Start Server)
```
```xml
   Return Format:
   
   bounds(String)
```
- return the first bounds of Node List of the real time xml with your key and value(equal).
```xml
  http://{your device ip:port}/getboundbykeyvalue?key={your key}&value={your value}

  (such as http://{your device ip:port}/getboundbykeyvalue?key=text&value=Start Server)
```
```xml
   Return Format:
   
   bounds(String)
```
------------

### Contact Me

mr3317952@gmail.com

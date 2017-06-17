# 对象 Smtp
Smtp对象

## 构造函数
        
### Smtp
Smtp 对象构造函数
```JavaScript
 new Smtp();
```

## 函数
        
### connect
建立到指定的服务器
```JavaScript
Smtp.connect(String url) async;
```

调用参数:
* url - 指定连接的协议，可以是：tcp://host:port 或者 ssl://host:port

### command
发送指定命令，并返回响应，服务器报错则抛出错误
```JavaScript
String Smtp.command(String cmd,
                String arg) async;
```

调用参数:
* cmd - 命令名
* arg - 参数

返回结果:
* 如果成功，返回服务器响应

### hello
发送 HELO 命令，服务器报错则抛出错误
```JavaScript
Smtp.hello(String hostname = "localhost") async;
```

调用参数:
* hostname - 主机名，缺省为“localhost”

### login
用指定的用户及密码登录服务器，服务器报错则抛出错误
```JavaScript
Smtp.login(String username,
                String password) async;
```

调用参数:
* username - 用户名
* password - 密码

### from
指定发件人信箱，服务器报错则抛出错误
```JavaScript
Smtp.from(String address) async;
```

调用参数:
* address - 发件人信箱

### to
指定收件人信箱，服务器报错则抛出错误
```JavaScript
Smtp.to(String address) async;
```

调用参数:
* address - 收件人信箱

### data
发送文本到收件人，服务器报错则抛出错误
```JavaScript
Smtp.data(String txt) async;
```

调用参数:
* txt - 要发送的文本

### quit
退出并关闭连接，服务器报错则抛出错误
```JavaScript
Smtp.quit() async;
```

### dispose
强制回收对象，调用此方法后，对象资源将立即释放
```JavaScript
Smtp.dispose();
```

### equals
比较当前对象与给定的对象是否相等
```JavaScript
Boolean Smtp.equals(object expected);
```

调用参数:
* expected - 制定比较的目标对象

返回结果:
* 返回对象比较的结果

### toString
返回对象的字符串表示，一般返回 &#34;[Native Object]&#34;，对象可以根据自己的特性重新实现
```JavaScript
String Smtp.toString();
```

返回结果:
* 返回对象的字符串表示

### toJSON
返回对象的 JSON 格式表示，一般返回对象定义的可读属性集合
```JavaScript
Value Smtp.toJSON(String key = "");
```

调用参数:
* key - 未使用

返回结果:
* 返回包含可 JSON 序列化的值

### valueOf
返回对象本身的数值
```JavaScript
Value Smtp.valueOf();
```

返回结果:
* 返回对象本身的数值

## 属性
        
### timeout
查询和设置超时时间 单位毫秒
```JavaScript
Integer Smtp.timeout;
```

### socket
查询 Smtp 对象当前连接的 Socket
```JavaScript
readonly Stream Smtp.socket;
```

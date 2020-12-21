# 安全文件传输系统
​	基于OpenSSL的文件传输系统的设计与实现，使用线程池技术

## 签发数字证书

```bash
# 产生私钥
openssl genrsa -out privkey.pem 2048
# 产生公钥
openssl req -new -x509 -key privkey.pem -out cacert.pem -days 1095
```




## Server
​	服务器端代码

### 服务器端编译运行

编译命令如下：

``` bash
gcc -o server server.c -lssl -lcrypto -pthread 
```

运行命令如下：

```bash
./server
```

## Client
​	存放客户端代码

### 客户端编译运行

编译命令如下：

```
gcc -o client client.c -lssl -lcrypto -pthread 
```

运行命令如下：

```
./client 127.0.0.1 (服务器ip地址)
```


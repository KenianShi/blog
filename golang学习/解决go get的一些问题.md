## 下载grpc-go源码
在GOPATH/src路径下操作
```
## 下载grpc-go源码
git clone https://github.com/grpc/grpc-go ./google.golang.org/grpc

## 安装grpc,以下操作很可能会失败，因为缺少依赖包，后续内容进行安装依赖包
go install google.golang.org/grpc  
```

## 安装golang.org/x/net 包和genproto包
```
git clone https://github.com/golang/net.git ./golang.org/x/net

git clone https://github.com/google/go-genproto.git ./google.golang.org/genproto

```

## 安装text包
```
git clone https://github.com/golang/text.git ./golang.org/x/text

```
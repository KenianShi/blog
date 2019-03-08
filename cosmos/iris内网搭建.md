# iris内网搭建

在做cosmos的测试的时候，可能出现没有测试网，或者测试网没有水龙头，没有币等。这时候可可以自己搭建一条测试链出来，其实很简单

### 安装iris
这一步操作文档就不提供了，有什么问题直接去官方文档

### 初始化节点
- 创建账户，记好助记词，这是恢复账号的关键
```
    iriscli keys add {Tom}
```


### 初始化genesis.json和config.toml配置文件
```
    iris init --chain-id=001 --moniker{you node name}
```
这步操作可以指定 --home={your path}，
- 如果指定的话则会在指定的path下面生成config文件夹
- 如果没有指定的话，则会生成~/.iris文件夹，

创建申请成为验证人的交易
```
    iris gentx --name={account_name} 
```
此操作将在{path_to_your_home}/config/gentx

如果之前init操作指定了--home目录的话，这里也需要指定。如果

### 配置genesis
将账户添加到genesis.json
```
iris add-genesis-account iva1u9pxhlqp9epu5uvmtyce3mkanhkd7xgapc2vq6 1500iris
```

收集gentx,如果之前制定了--home，这时继续需要指定
```
    iris collect-gentxs 
```
这一步,就将账户写入到genesis里面了，剩下的只需要启动这个链即可

### 启动节点网络
```
    iris start > log.log &
```
以后台防止运行，并把日志打印到log.log文件中


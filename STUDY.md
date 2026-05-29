# 学习笔记

## 钱包管理
1. 系统中没有钱的概念，只有额度quota
2. user.quota 即当前余额
   1. 充值：model/user.go:900
   2. 消费：model/user.go:908

## completion 

跟踪请求，怎么发给外部AI


## 启动

1. 运行 `makefile` 构建前端页面文件
2. 运行 `main.go` 启动后端服务，前端文件也会打包到gin中 
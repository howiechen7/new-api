# 学习笔记

## 钱包管理
1. 系统中没有钱的概念，只有额度quota
2. user.quota 即当前余额
   1. 充值：model/user.go:900
   2. 消费：model/user.go:908

## completion 

跟踪请求，怎么发给外部AI

1. claude 调用路径：/v1/messages
2. openai 调用路径：/v1/responses

请求链路

1. relay-router.go SetRelayRouter
2. 进入 /v1/messages
3. relay.go Relay
4. claude_handler.go ClaudeHelper
5. adaptor.go DoRequest
6. api_request.go DoApiRequest

## 初始化数据库

1. model/main.go chooseDB。选择数据库
2. 借助ORM框架gorm，自动根据实体创建表结构。实体字段变更后也会自动同步

## 启动

1. 运行 `makefile` 构建前端页面文件
2. 运行 `main.go` 启动后端服务，前端文件也会打包到gin中 
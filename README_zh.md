# go-coffeeshop (中文版)

一个基于事件驱动的微服务咖啡店应用，使用 Golang 开发，并通过 Nomad、Consul Connect、Vault 和 Terraform 部署。

其他语言版本：
- [.NET 微服务版本](https://github.com/thangchung/coffeeshop-on-nomad)
- [.NET 模块化单体版本](https://github.com/thangchung/coffeeshop-modular)

## 技术栈

### 后端构建块
- **核心框架**
  - [gRPC网关](https://github.com/grpc-ecosystem/grpc-gateway)
  - [Echo Web框架](https://github.com/labstack/echo)
  - [RabbitMQ客户端](https://github.com/rabbitmq/amqp091-go)
  
- **数据库工具**
  - [SQL代码生成器](https://github.com/kyleconroy/sqlc)
    - [PostgreSQL驱动](github.com/lib/pq)
  - [数据库迁移工具](https://github.com/golang-migrate/migrate)

- **实用工具**
  - [依赖注入](github.com/google/wire)
  - [配置管理](https://github.com/ilyakaznacheev/cleanenv)
  - 日志工具
    - [结构化日志](golang.org/x/exp/slog)
    - [Logrus日志库](https://github.com/sirupsen/logrus)
  - [Lodash风格工具集](https://github.com/samber/lo)
  - [CPU核心管理](go.uber.org/automaxprocs/maxprocs)
  - [测试框架](github.com/stretchr/testify)
  - 其他Google工具集

### 基础设施
- **数据服务**: PostgreSQL, RabbitMQ
- **HashiCorp生态**: Nomad, Consul Connect, Vault, Terraform
- **容器化**: Docker和Docker Compose
- **开发环境**: Devcontainer标准化配置

## 咖啡店-编排式Saga架构

![架构图](docs/coffeeshop.svg)

## 服务列表

序号 | 服务名称 | 访问地址
--- | --- | ---
1 | gRPC网关 | [http://localhost:5000](http://localhost:5000) 
2 | 产品服务 | [http://localhost:5001](http://localhost:5001)
3 | 柜台服务 | [http://localhost:5002](http://localhost:5002)
4 | 咖啡师服务 | 仅后台工作
5 | 厨房服务 | 仅后台工作 
6 | 前端界面 | [http://localhost:8888](http://localhost:8888)

## 快速启动

1. 进入[开发容器配置](https://code.visualstudio.com/docs/devcontainers/containers)
2. 执行命令：
```bash
make docker-compose
```

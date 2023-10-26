---
layout: post
title: Docker cheatsheet
date: 2023-10-09 20:08:02 +/-5000
categories: [env]
tags: [docker]     # TAG names should always be lowercase
---
# Docker cheatsheet 

## Useful commands 
| Command/Aspect        | Docker Image Command (镜像命令)                | Docker Container Command (容器命令)          |
|-----------------------|----------------------------------------------|----------------------------------------------|
| 创建 (Create)         | `docker build`                             | `docker run`                                |
| 查看列表 (List)       | `docker images`                            | `docker ps`                                 |
| 启动 (Start)          |                                              | 启动容器 (`docker start`)                   |
| 停止 (Stop)           |                                              | 停止容器 (`docker stop`)                    |
| 移除 (Remove)         |                                              | 移除容器 (`docker rm`)                      |
| 进入 (Exec into)      |                                              | 进入容器 (`docker exec`)                    |
| 查看日志 (View Logs)  |                                              | 查看容器日志 (`docker logs`)                |
| 复制文件 (Copy Files) |                                              | 复制文件到/从容器 (`docker cp`)              |
| 查看详细信息 (Inspect Details) | `docker inspect`                 | `docker inspect`                            |
| 暂停/取消暂停 (Pause/Unpause) |                                      | 暂停/取消暂停容器 (`docker pause`, `docker unpause`) |
| 重命名容器 (Rename Container) |                                    | 重命名容器 (`docker rename`)                |
| 连接到容器 (Attach to Container) |                                  | 连接到容器 (`docker attach`)                 |
| 查看端口映射 (View Port Mapping) |                                | 查看端口映射 (`docker port`)                |
| 查看环境变量 (Environment Variables) |                            | 查看容器环境变量 (`docker inspect -f '{{.Config.Env}}'`) |
| 查看统计信息 (Statistics) |                                        | 查看容器资源使用情况 (`docker stats`)     |
| 清理未使用的镜像 (Prune Unused Images) | `docker image prune`       |                                              |
| 清理未使用的容器 (Prune Unused Containers) |                                  | 清理未使用的容器 (`docker container prune`) |
| 网络配置 (Network Configuration) |                                  | 网络配置 (`docker network`)                 |
| 暂停所有容器 (Pause All Containers) |                                | 暂停所有容器 (`docker pause $(docker ps -q)`) |
| 取消暂停所有容器 (Unpause All Containers) |                          | 取消暂停所有容器 (`docker unpause $(docker ps -q)`) |
| 查看容器日志 (Container Logs) |                                      | 查看容器日志 (`docker container logs`)    |


I found this [docker official cheatsheet](https://docs.docker.com/get-started/docker_cheatsheet.pdf) really useful. 

## Docker Compose 
### 工作流程
| 步骤                         | 操作                                       |
| ---------------------------- | ------------------------------------------ |
| 写 Dockerfile               | 写 Dockerfile，包含所需环境和依赖。           |
| 构建 Docker 镜像             | `docker build`，从 Dockerfile 创建 Docker 镜像。 |
| 写 Docker Compose 文件        | 写 `docker-compose.yml`，定义应用程序的服务、容器关系、端口映射和环境变量。 |
| 使用 Docker Compose 启动容器 |  `docker-compose up`，Docker Compose 根据配置创建和启动容器实例。 |
| 管理容器                     | 使用 Docker Compose 命令方便地管理容器，如停止、重新启动、查看日志等。     |

### 具体command
**步骤 1: 编写 Dockerfile**

```
# 使用 Node.js 官方镜像作为基础镜像
FROM node:14

# 设置工作目录
WORKDIR /app

# 复制应用程序的依赖文件
COPY package*.json ./

# 安装依赖
RUN npm install

# 复制应用程序代码
COPY . .

# 暴露应用程序端口
EXPOSE 3000

# 启动应用程序
CMD ["node", "app.js"]
```

**步骤 2: 构建 Docker 镜像**

```
docker build -t my-node-app:1.0 .
```

**步骤 3: 编写 Docker Compose 文件**

创建一个名为 `docker-compose.yml` 的文件，定义一个 Node.js 服务以及与之相关的容器配置和关系：

```
version: '3'
services:
  my-app:
    image: my-node-app:1.0
    ports:
      - "3000:3000"
    environment:
      NODE_ENV: production
```
这个 Compose 文件定义了一个名为 my-app 的服务，使用了前面构建的镜像，并将容器内的端口 3000 映射到主机的端口 3000，同时设置了 NODE_ENV 环境变量。

**步骤 4: 使用 Docker Compose 启动容器**

在包含 docker-compose.yml 文件的目录中，使用以下命令启动容器，这将启动应用程序容器并在后台运行。：

```
docker-compose up -d
```


**步骤 5: 管理容器**

停止容器
```
docker-compose down
```
查看容器的日志输出
```
docker-compose logs
```


## My FAQ 

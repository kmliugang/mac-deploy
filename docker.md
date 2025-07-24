# Docker 文档

## 简介
Docker 是一个用于开发、部署和运行容器化应用的平台。容器允许开发者将应用及其所有依赖项打包成一个标准化的单元。

## 安装
1. 从 [Docker 官方网站](https://www.docker.com/) 下载 Docker。
2. 根据您的操作系统，按照安装说明进行操作。

## 基本命令
### 启动 Docker
```bash
docker start
```

### 拉取镜像
```bash
docker pull <镜像名称>
```

### 运行容器
```bash
docker run <镜像名称>
```

### 列出容器
```bash
docker ps
```

### 停止容器
```bash
docker stop <容器 ID>
```

### 删除容器
```bash
docker rm <容器 ID>
```

### 删除镜像
```bash
docker rmi <镜像名称>
```

## Dockerfile 示例
```dockerfile
# 使用官方 Python 运行时作为基础镜像
FROM python:3.9-slim

# 设置工作目录
WORKDIR /app

# 将当前目录内容复制到容器中
COPY . /app

# 安装依赖项
RUN pip install --no-cache-dir -r requirements.txt

# 运行应用程序
CMD ["python", "app.py"]
```

## 资源
- [Docker 文档](https://docs.docker.com/)
- [Docker Hub](https://hub.docker.com/)

FROM node:18-alpine

WORKDIR /app

# 安装系统依赖
RUN apk add --no-cache git python3 make g++

# 复制你当前目录的所有源码到容器
COPY . .

# 设置国内源，加速安装
RUN npm config set registry https://registry.npmmirror.com

# 安装 pnpm
RUN npm install -g pnpm

# 安装项目依赖
RUN pnpm install

# 构建项目
RUN pnpm run build

# 暴露端口（dev-sidecar 默认端口）
EXPOSE 63000

# 启动
CMD ["pnpm", "start"]

# Hono Node.js Demo

一个基于 [Hono](https://hono.dev/) 框架的 Node.js Web 应用示例项目。Hono 是一个超快的 Web 框架，专为 Edge 运行时设计，同时支持 Node.js。

## 技术栈

- **Node.js**: 25.0.0 (通过 Volta 管理)
- **Hono**: 4.10.3
- **@hono/node-server**: 1.19.5 (Node.js 服务器适配器)
- **TypeScript**: 5.9.3
- **TSX**: 4.7.1 (TypeScript 执行器)

## 项目结构

```
hono-node-demo/
├── src/
│   ├── index.ts         # 应用入口，主路由配置
│   └── router/
│       └── users.ts     # 用户相关路由
├── package.json         # 项目依赖配置
├── tsconfig.json        # TypeScript 配置
├── index.http           # HTTP 请求测试文件
└── README.md
```

## 功能特性

- 基础路由处理 (`GET /`)
- 用户 API 路由 (`/api/v1/users`)
- 模块化路由结构
- TypeScript 支持
- 直接运行 TypeScript (无需编译)

## 快速开始

### 前置要求

- Node.js 25.0.0 或更高版本
- npm 或 yarn

### 安装和运行

```bash
# 克隆项目
git clone <repository-url>
cd hono-node-demo

# 安装依赖
npm install

# 运行项目（开发模式，直接运行 TypeScript）
npm start

# 或构建后运行
npm run build
node dist/index.js
```

服务将在 `http://localhost:3000` 启动。

### API 端点

#### 根路径
```http
GET http://localhost:3000/
```
响应: `Hello Hono!`

#### 获取所有用户
```http
GET http://localhost:3000/api/v1/users
```
响应示例:
```json
[
  {"id": 1, "name": "Alice"},
  {"id": 2, "name": "Bob"}
]
```

#### 获取单个用户
```http
GET http://localhost:3000/api/v1/users/:id
```
响应示例:
```json
{
  "id": 1,
  "name": "John Doe"
}
```

## 代码说明

### 主应用 (`src/index.ts`)

应用入口点，配置了以下内容：
- 创建 Hono 应用实例
- 注册用户路由 (`/`)
- 定义根路径处理器
- 使用 `@hono/node-server` 启动服务器

### 用户路由 (`src/router/users.ts`)

实现了用户相关的 API：
- `GET /api/v1/users`: 获取所有用户列表
- `GET /api/v1/users/:id`: 根据 ID 获取单个用户

## 开发

### 运行开发服务器

```bash
npm start
```

使用 TSX 直接运行 TypeScript 文件，支持热重载。

### 构建项目

```bash
npm run build
```

将 TypeScript 编译为 JavaScript。

## 测试

可以使用 `index.http` 文件中的 HTTP 请求进行测试，或使用 curl:

```bash
# 测试根路径
curl http://localhost:3000/

# 测试获取所有用户
curl http://localhost:3000/api/v1/users

# 测试获取单个用户
curl http://localhost:3000/api/v1/users/1
```

## 参考资源

- [Hono 官方网站](https://hono.dev/)
- [Hono CLI](https://blog.yusu.ke/hono-cli/): 用于人类和 AI 的 Hono CLI
- [Hono 文档](https://hono.dev/docs)

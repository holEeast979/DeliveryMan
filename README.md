# 暨大外卖平台 🍔

一个基于Vue.js + Flask + MySQL的完整外卖平台系统，实现用户点餐、订单管理、配送管理等核心功能。

## 📖 项目简介

本项目是一个数据库课程设计项目，模拟真实的外卖平台业务场景，包含用户端和管理端的完整功能。系统采用前后端分离的架构，通过RESTful API进行数据交互。

### 🎯 主要功能

#### 用户端功能
- **用户认证**：用户登录/注册
- **店铺浏览**：查看所有可用的快餐店铺及价格信息
- **订单管理**：
  - 下订单功能
  - 查看未发货订单（可修改、删除）
  - 查看配送中订单
  - 查看已完成订单
- **个人中心**：
  - 个人信息管理
  - 密码修改

#### 管理端功能
- **店铺管理**：添加、修改、删除快餐店铺信息
- **服务员管理**：管理店铺服务员信息
- **配送员管理**：配送员信息的增删改查
- **订单管理**：
  - 查看未发货订单并分配配送员
  - 查看配送中订单
  - 查看已完成订单
- **物流管理**：查看配送记录（已完成/进行中）

## 🏗️ 项目架构

```
HEU-Database-course-design/
├── 前端代码/          # Vue.js前端项目
│   └── sjk/
│       ├── src/
│       │   ├── components/    # Vue组件
│       │   ├── router/       # 路由配置
│       │   └── api/          # API接口
│       └── package.json
├── 后端代码/          # Flask后端项目
│   ├── app.py        # 主应用文件
│   ├── config.py     # 数据库配置
│   ├── auth.py       # JWT认证
│   └── requirements.txt
└── 数据库代码/        # MySQL数据库脚本
    └── delivery.sql
```

## 🛠️ 技术栈

### 前端技术
- **Vue.js 2.6.14** - 前端框架
- **Element UI 2.15.12** - UI组件库
- **Vue Router 3.5.2** - 路由管理
- **Axios 1.2.0** - HTTP客户端

### 后端技术
- **Flask 2.3.3** - Web框架
- **SQLAlchemy 2.0.23** - ORM框架
- **Flask-CORS** - 跨域支持
- **PyJWT 2.8.0** - JWT认证
- **Redis 5.0.1** - 缓存数据库
- **PyMySQL 1.1.0** - MySQL驱动

### 数据库
- **MySQL 8.0** - 主数据库
- **Redis** - 缓存数据库

## 🚀 快速开始

### 环境要求
- Python 3.7+
- Node.js 14+
- MySQL 8.0+
- Redis

### 1. 数据库设置

```bash
# 1. 创建数据库
mysql -u root -p
CREATE DATABASE zhd_sql_ks CHARACTER SET utf8mb4;

# 2. 导入数据库脚本
mysql -u root -p zhd_sql_ks < 数据库代码/delivery.sql
```

### 2. 后端设置

```bash
# 1. 进入后端目录
cd 后端代码/

# 2. 创建虚拟环境
python -m venv venv

# 3. 激活虚拟环境
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate

# 4. 安装依赖
pip install -r requirements.txt

# 5. 配置数据库连接
# 编辑 config.py 文件，修改数据库连接参数

# 6. 启动后端服务
python app.py
```

### 3. 前端设置

```bash
# 1. 进入前端目录
cd 前端代码/sjk/

# 2. 安装依赖
npm install

# 3. 启动开发服务器
npm run serve

# 4. 构建生产版本
npm run build
```

### 4. Redis设置

```bash
# 启动Redis服务
redis-server
```

## 🎮 使用说明

### 访问地址
- 前端地址：http://localhost:8080
- 后端API：http://localhost:5000

### 默认账户
请查看数据库初始数据或联系开发者获取测试账户信息。

## 📊 数据库设计

### 核心数据表
- **user** - 用户信息表
- **fastfood_shop** - 快餐店铺表
- **server** - 服务员表
- **dispatcher** - 配送员表
- **oorder** - 订单表
- **wuliu** - 物流表
- **user_msg** - 用户详细信息表
- **sending_order** - 配送中订单视图
- **sended_order** - 已完成订单视图

## 🔧 开发说明

### API接口

#### 用户相关
- `POST /api/user/login` - 用户登录
- `GET /api/user/shop` - 获取店铺信息
- `POST /api/user/addorder` - 下订单
- `GET /api/user/unsend` - 获取未发货订单
- `GET /api/user/sending` - 获取配送中订单
- `GET /api/user/sended` - 获取已完成订单

#### 管理员相关
- `GET /api/manager/shop` - 店铺管理
- `GET /api/manager/server` - 服务员管理
- `GET /api/manager/dispatcher` - 配送员管理
- `GET /api/manager/unsend` - 订单分配
- `GET /api/manager/wuliu` - 物流管理

### 项目特色
1. **完整的业务流程**：从下单到配送的完整流程管理
2. **角色权限分离**：用户端和管理端功能分离
3. **响应式设计**：基于Element UI的现代化界面
4. **RESTful API**：标准的API设计规范
5. **JWT认证**：安全的用户认证机制

## 🤝 贡献指南

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开 Pull Request

## 📄 许可证

本项目为学习用途的数据库课程设计项目。


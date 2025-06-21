# 接单平台

## 技术栈

### 后端技术栈
- **Python**: >= 3.11.0 (最低3.9+版本)
- **Django**: 3.2
- **Django REST Framework**: API开发框架
- **JWT**: djangorestframework-simplejwt 认证
- **数据库**: MySQL >= 8.0 / SQLite3
- **缓存**: Redis

### 前端技术栈
- **Vue**: 3.x
- **TypeScript**: 类型支持
- **Vite**: 构建工具
- **Element Plus**: UI组件库
- **Pinia**: 状态管理
- **Composition API**: Vue3组合式API
- **Node.js**: >= 16.0

### 开发环境要求
- Python >= 3.11.0
- Node.js >= 16.0
- MySQL >= 8.0 (可选)
- Redis (可选)

### 浏览器支持
| Edge | Firefox | Chrome | Safari |
|------|---------|--------|---------|
| ≥ 79 | ≥ 78    | ≥ 64   | ≥ 12   |

### 核心特性
- 前后端分离架构
- RBAC权限模型
- JWT多终端认证
- 动态权限菜单
- 列级权限控制
- RESTful API设计

## 部署方式

### Docker部署
```bash
# 使用docker-compose一键部署
docker-compose up -d

# 初始化数据库
docker exec -ti dvadmin3-django bash
python manage.py makemigrations
python manage.py migrate
python manage.py init_area
python manage.py init
exit
```

### 手动部署

#### 后端部署
```bash
# 1. 进入后端目录
cd backend

# 2. 配置环境文件
cp ./conf/env.example.py ./conf/env.py

# 3. 安装依赖
pip3 install -r requirements.txt

# 4. 数据库迁移
python3 manage.py makemigrations
python3 manage.py migrate

# 5. 初始化数据
python3 manage.py init
python3 manage.py init_area

# 6. 启动服务
python3 manage.py runserver 0.0.0.0:8000
# 或使用uvicorn
uvicorn application.asgi:application --port 8000 --host 0.0.0.0 --workers 8
```

#### 前端部署
```bash
# 1. 进入前端目录
cd web

# 2. 安装依赖
yarn install --registry=https://registry.npmmirror.com

# 3. 构建生产版本
yarn build

# 4. 启动开发服务器
yarn dev
```

### 生产环境配置
- **Web服务器**: Nginx
- **应用服务器**: Gunicorn/Uvicorn
- **数据库**: MySQL 8.0+
- **缓存**: Redis
- **容器化**: Docker + Docker Compose

### 访问地址
- 前端: http://localhost:8080
- 后端API: http://localhost:8000/api
- 默认账号: superadmin / admin123456

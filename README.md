# 智慧人防工程宣传系统

> 基于物联网与VR技术的现代化人防工程监控与宣教平台

## 项目简介

本项目是一个综合性的人防工程宣传管理系统，集成了物联网设备监控、VR全景展示、人防知识普及和应急演练指导等功能。系统采用前后端分离架构，提供现代化的用户交互体验和高效的数据管理能力。

## 项目截图

![首页](https://cdn.jsdelivr.net/gh/codearts-cn/codearts-cdn@main/images/civil-defense-project/index.png)

![设备监控](https://cdn.jsdelivr.net/gh/codearts-cn/codearts-cdn@main/images/civil-defense-project/device-monitor.png)

![VR全景展示](https://cdn.jsdelivr.net/gh/codearts-cn/codearts-cdn@main/images/civil-defense-project/vr-panorama.png)

![知识普及](https://cdn.jsdelivr.net/gh/codearts-cn/codearts-cdn@main/images/civil-defense-project/knowledge-guide.png)

![应急演练](https://cdn.jsdelivr.net/gh/codearts-cn/codearts-cdn@main/images/civil-defense-project/drill-steps.png)

![数据统计](https://cdn.jsdelivr.net/gh/codearts-cn/codearts-cdn@main/images/civil-defense-project/statistics.png)

![联系反馈](https://cdn.jsdelivr.net/gh/codearts-cn/codearts-cdn@main/images/civil-defense-project/contact-feedback.png)

![]

## 核心功能

- **设备监控**：实时监测人防工程内各类设备的运行状态
- **VR全景展示**：基于WebVR技术的人防工程全景漫游
- **知识普及**：系统化的人防知识库和教育内容
- **应急演练**：交互式的人防应急演练指导流程
- **数据统计**：可视化的人防工程运行数据分析
- **联系反馈**：便捷的用户联系和意见反馈渠道

## 技术架构

### 前端技术栈
- **框架**：Vue 3 (Composition API)
- **样式**：Tailwind CSS
- **3D渲染**：Three.js (VR全景)
- **地图服务**：Leaflet
- **图标库**：FontAwesome

### 后端技术栈
- **语言**：PHP 8.1+
- **框架**：Webman (高性能常驻内存框架)
- **ORM**：Think ORM
- **数据库**：MySQL 5.7+
- **依赖管理**：Composer

## 项目结构

```
civil-defense-project/
├── frontend/                    # 前端项目
│   ├── index.html              # 主应用入口
│   ├── test_3d.html            # 3D功能测试页面
│   └── nginx.conf              # Nginx配置文件
├── backend/                     # 后端项目
│   ├── app/                    # 应用核心代码
│   │   ├── api/                # API接口层
│   │   │   └── controller/     # 控制器
│   │   ├── middleware/         # 中间件
│   │   └── service/            # 业务服务层
│   ├── config/                 # 配置文件
│   ├── database/               # 数据库脚本
│   │   ├── init.sql            # 数据库初始化
│   │   ├── reset.sql           # 数据库重置
│   │   └── reset.bat           # Windows重置脚本
│   ├── public/                 # 公共资源目录
│   ├── support/                # 框架支持文件
│   ├── composer.json           # Composer配置
│   ├── .env.example            # 环境变量模板
│   ├── start.php               # 应用启动文件
│   └── nginx.conf              # Nginx配置文件
├── README.md                   # 项目说明文档
├── QUICKSTART.md              # 快速开始指南
├── API.md                     # API接口文档
└── DEPLOY.md                  # 部署指南
```

## 快速开始

### 环境要求
- PHP >= 8.1
- MySQL >= 5.7
- Nginx >= 1.18
- Composer >= 2.0

### 安装步骤

1. **克隆项目**
```bash
git clone <repository-url>
cd civil-defense-project
```

2. **数据库配置**
```bash
# 登录MySQL
mysql -u root -p

# 创建数据库
CREATE DATABASE civil_defense CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

# 导入初始化脚本
USE civil_defense;
SOURCE backend/database/init.sql;
```

3. **后端配置**
```bash
cd backend

# 安装依赖
composer install

# 配置环境变量
cp .env.example .env
# 编辑 .env 文件，配置数据库连接信息
```

4. **启动后端服务**
```bash
# 开发环境
php start.php start

# 生产环境（守护进程）
php start.php start -d
```

后端服务默认运行在 `http://localhost:8787`

5. **启动前端服务**
```bash
cd frontend

# 使用Python简单HTTP服务器（开发环境）
python -m http.server 3000

# 或使用其他HTTP服务器
```

前端服务默认运行在 `http://localhost:3000`

## API接口

系统提供RESTful API接口，详细文档请参考 [API.md](./API.md)

主要接口包括：
- 统计数据接口
- 设备管理接口
- 人防知识接口
- 演练流程接口
- 全景展示接口
- 联系反馈接口

## 数据库设计

系统包含以下核心数据表：

| 表名 | 说明 |
|------|------|
| `cd_devices` | 设备信息管理 |
| `cd_knowledge` | 人防知识库 |
| `cd_drill_steps` | 应急演练流程 |
| `cd_panorama` | VR全景数据 |
| `cd_contact_info` | 联系信息管理 |
| `cd_feedback` | 用户反馈记录 |
| `cd_statistics` | 统计数据存储 |

## 部署指南

详细的生产环境部署指南请参考 [DEPLOY.md](./DEPLOY.md)

主要部署步骤：
1. 服务器环境准备
2. 数据库配置与初始化
3. 后端服务部署
4. 前端资源部署
5. Nginx配置
6. 安全加固

## 开发指南

### 代码规范
- 前端遵循Vue 3官方风格指南
- 后端遵循PSR-12编码标准
- 使用语义化版本控制

### 提交规范
```
feat: 新功能
fix: 修复bug
docs: 文档更新
style: 代码格式调整
refactor: 代码重构
test: 测试相关
chore: 构建/工具链相关
```

## 常见问题

### 后端启动失败
- 检查PHP版本是否符合要求
- 确认Composer依赖已完整安装
- 验证数据库连接配置是否正确

### 前端无法连接后端
- 确认后端服务正常运行
- 检查API地址配置
- 查看浏览器控制台跨域错误信息

### 数据库连接问题
- 确认MySQL服务已启动
- 验证数据库用户权限
- 检查.env文件中的数据库配置

## 项目维护

### 开发者信息
- **项目负责人**：[您的姓名/化名]
- **技术架构**：Vue3 + Webman + Three.js
- **项目状态**：开发中

### 版本历史
- v1.0.0 - 初始版本发布

## 许可证

本项目仅供学习交流使用。

## 致谢

感谢所有为本项目做出贡献的开发者和使用者。

---

如有问题或建议，欢迎通过项目内的联系反馈渠道与我们交流。
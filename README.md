# 小学英语词汇学习应用

一个基于 Spring Boot 和 Vue.js 构建的应用程序，旨在通过互动练习帮助小学生学习和记忆英语词汇。

## 技术栈

### 后端
- **Spring Boot**: 用于构建 RESTful API
- **JPA/Hibernate**: 数据持久化
- **H2 数据库**: 开发环境使用的内存数据库
- **Swagger/OpenAPI**: API 文档自动生成

### 前端
- **Vue 3**: 前端框架，使用 Composition API
- **Vuex**: 状态管理
- **Vue Router**: 路由管理
- **Web Speech API**: 实现文本转语音功能

## 功能特点

- 按年级(1-6年级)分类的词汇学习
- 基于级别的渐进式学习方法
- 单词发音功能
- 互动式打字练习
- 计时器和分数跟踪
- 用户进度记录
- 针对儿童设计的友好界面

## 项目结构

```
spring-boot-vue-vocabulary-app/
├── backend/                 # Spring Boot 后端
│   ├── src/                 
│   │   ├── main/java/com/vocabulary/app/
│   │   │   ├── config/      # 应用配置
│   │   │   ├── controller/  # REST 控制器
│   │   │   ├── exception/   # 异常处理
│   │   │   ├── model/       # 数据模型
│   │   │   ├── repository/  # 数据访问层
│   │   │   ├── service/     # 业务逻辑层
│   │   └── resources/       # 配置文件
│   └── pom.xml              # Maven 依赖
│
├── frontend/                # Vue.js 前端
    ├── public/              # 静态文件
    ├── src/                 
    │   ├── assets/          # 图片等资源
    │   ├── components/      # Vue 组件
    │   ├── router/          # 路由配置
    │   ├── services/        # API 服务
    │   ├── store/           # Vuex 状态管理
    │   ├── views/           # 页面视图
    │   ├── App.vue          # 根组件
    │   └── main.js          # 入口文件
    └── package.json         # npm 依赖
```

## 开始使用

### 前提条件

- Java 11+
- Node.js 和 npm
- Maven

### 运行后端

```bash
cd spring-boot-vue-vocabulary-app/backend
mvn spring-boot:run
```

后端服务将在 `http://localhost:8080/api` 启动。

### 运行前端

```bash
cd spring-boot-vue-vocabulary-app/frontend
npm install
npm run serve
```

前端应用将在 `http://localhost:8081` 启动。

## API 文档

应用集成了 Swagger OpenAPI 文档，启动后端后可通过以下地址访问：

```
http://localhost:8080/api/swagger-ui.html
```

API 文档提供了所有可用端点的详细说明、请求参数和响应格式。

## 主要 API 端点

### 年级管理
- `GET /api/grades` - 获取所有年级
- `GET /api/grades/{id}` - 获取指定年级

### 级别管理
- `GET /api/levels` - 获取所有级别
- `GET /api/levels/grade/{gradeId}` - 获取指定年级的级别

### 词汇管理
- `GET /api/words` - 获取所有单词
- `GET /api/words/level/{levelId}` - 获取指定级别的单词
- `GET /api/words/search?query={query}` - 搜索单词

### 用户和进度
- `POST /api/users` - 创建新用户
- `GET /api/users/username/{username}` - 获取用户信息
- `POST /api/progress/start` - 开始学习会话
- `POST /api/progress/{id}/complete` - 完成学习会话

## 未来计划

- 用户认证系统
- 扩展词汇库
- 增加更多互动游戏模式
- 实现语音识别功能
- 开发移动应用版本

## 许可证

本项目采用 MIT 许可证。 

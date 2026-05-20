# campus-market

校园二手市场系统，基于 Spring Boot、Spring Data JPA、FreeMarker 和 MySQL 构建，适用于校园内二手商品发布、浏览、求购、交易沟通和后台管理等场景。

## 项目简介

本项目包含前台用户端和后台管理端两部分：

- 前台用户端：面向学生用户，提供商品浏览、商品详情、商品发布、求购发布、用户中心、登录注册、评论和举报等功能。
- 后台管理端：面向管理员，提供用户、角色、菜单、商品、商品分类、求购信息、新闻、友情链接、站点设置、评论、举报和数据库备份等管理功能。

## 技术栈

- 后端：Java 8、Spring Boot 2.1.0.RELEASE、Spring MVC、Spring Data JPA
- 模板：FreeMarker
- 数据库：MySQL
- 前端：Bootstrap、jQuery
- 构建工具：Maven

## 功能模块

### 前台功能

- 首页商品展示
- 商品分类浏览
- 商品详情查看
- 学生用户注册、登录和退出
- 发布、编辑二手商品
- 发布、编辑求购信息
- 用户中心
- 商品评论
- 商品举报
- 图片上传和访问

### 后台功能

- 管理员登录
- 用户管理
- 角色管理
- 菜单管理
- 商品分类管理
- 商品管理
- 求购信息管理
- 学生信息管理
- 新闻管理
- 友情链接管理
- 评论管理
- 举报管理
- 站点设置
- 操作日志
- 数据库备份

## 目录结构

```text
campus-market
├── pom.xml
├── src
│   ├── main
│   │   ├── java/com/yuanlrc/campus_market
│   │   │   ├── config        # Web、站点等配置
│   │   │   ├── controller    # 前台、后台、公共控制器
│   │   │   ├── dao           # JPA 数据访问层
│   │   │   ├── entity        # 实体类
│   │   │   ├── interceptor   # 登录和权限拦截器
│   │   │   ├── service       # 业务逻辑层
│   │   │   └── util          # 工具类
│   │   └── resources
│   │       ├── backup        # 数据库备份 SQL
│   │       ├── static        # 静态资源
│   │       ├── templates     # FreeMarker 页面模板
│   │       └── upload        # 示例上传资源
│   └── test
└── README.md
```

## 环境要求

- JDK 1.8
- Maven 3.x
- MySQL 5.7 或 8.x

## 快速启动

1. 创建数据库，例如：

```sql
CREATE DATABASE db_campus_market DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;
```

2. 按需导入 `src/main/resources/backup` 目录下的 SQL 备份文件。

3. 修改开发环境数据库配置：

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/db_campus_market?serverTimezone=GMT%2b8&useUnicode=true&characterEncoding=utf8
spring.datasource.username=root
spring.datasource.password=123456
```

配置文件路径：

```text
src/main/resources/application-dev.properties
```

4. 启动项目：

```bash
mvn spring-boot:run
```

5. 浏览器访问：

```text
http://localhost:8081
```

默认端口配置位于：

```text
src/main/resources/application.properties
```

## 打包运行

```bash
mvn clean package
java -jar target/campus-market-0.0.1-SNAPSHOT.jar
```

## 配置说明

- `spring.profiles.active=dev`：默认启用开发环境配置。
- `spring.jpa.hibernate.ddl-auto=update`：启动时自动同步实体和数据库表结构。
- `spring.servlet.multipart.maxFileSize=2MB`：上传文件大小限制。
- `ylrc.upload.photo.sufix`：允许上传的图片后缀。
- `ylrc.database.backup.*`：数据库备份相关配置。

## 注意事项

- 当前配置文件中包含示例数据库账号和密码，公开部署或公开仓库使用时，建议改为环境变量或本地私有配置。
- `target/`、IDE 配置和临时文件已通过 `.gitignore` 排除，不建议提交构建产物。
- 项目中的 `src/main/resources/upload` 包含示例图片资源，生产环境建议使用独立的文件存储目录。
- 若启动时报数据库连接错误，请先确认 MySQL 服务、数据库名称、账号密码和端口配置是否正确。

## 许可证

本项目当前未声明开源许可证。如需公开复用，请先补充 LICENSE 文件。

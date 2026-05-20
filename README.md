# campus-market

校园二手市场系统，基于 Spring Boot、Spring Data JPA、FreeMarker 和 MySQL 构建。

## 项目简介

本项目面向校园二手交易场景，包含前台用户端和后台管理端：

- 前台：商品浏览、商品发布、求购信息、用户注册登录、评论和举报等功能。
- 后台：用户、角色、菜单、商品分类、商品、求购、新闻、友情链接、站点设置、评论、举报和数据库备份管理。
- 技术栈：Java 8、Spring Boot 2.1、Spring Data JPA、FreeMarker、MySQL、Bootstrap/jQuery。

## 运行说明

1. 准备 Java 8、Maven 和 MySQL。
2. 创建数据库，并按需导入 `src/main/resources/backup` 下的 SQL 备份。
3. 修改 `src/main/resources/application-dev.properties` 中的数据库连接信息。
4. 启动项目：

```bash
mvn spring-boot:run
```

默认端口为 `8081`。

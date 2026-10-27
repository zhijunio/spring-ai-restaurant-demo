# Spring AI 智能餐厅推荐 Demo

[![Java](https://img.shields.io/badge/Java-21-blue?logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.2-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Spring AI](https://img.shields.io/badge/Spring%20AI-2.0.2-6DB33F?logo=spring&logoColor=white)](https://spring.io/projects/spring-ai)
[![Maven](https://img.shields.io/badge/Maven-3.10.0-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![GitHub stars](https://img.shields.io/github/stars/zhijunio/spring-ai-restaurant-demo)](https://github.com/zhijunio/spring-ai-restaurant-demo/stargazers)
[![许可证](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](LICENSE)

简体中文 | [English](README.md)

这是一个基于 Spring AI 的餐厅推荐示例，涵盖餐饮对话、结构化输出和检索增强生成（RAG）。项目使用 PostgreSQL/pgvector，还包括流式响应、工具调用、高级检索示例和情感分析。

## 功能

- 餐厅、菜品推荐，用餐建议和对话
- RAG 文档加载、语义检索和个性化对话
- 通过 Server-Sent Events 流式返回聊天和推荐结果
- Function Calling、重排序、混合检索、多查询检索和情感分析
- 使用 PostgreSQL/pgvector 保存向量

## 环境要求

- JDK 21
- [mise](https://mise.jdx.dev/)（用于安装项目指定的 Java 和 Maven 版本）
- Docker Compose
- 默认模型 profile 需要 OpenAI API Key

## 本地运行

安装项目工具链，并启动 PostgreSQL/pgvector：

```bash
mise install
docker compose up -d
```

设置 API Key 并运行应用：

```bash
export OPENAI_API_KEY=your-api-key
./mvnw spring-boot:run
```

打开 <http://localhost:8080/>。Maven 默认启用 `open-ai` profile。其他已配置的 profile 为 `mistral-ai` 和 `ollama-ai`；提供方配置见 `src/main/resources/application.yml`。

## 接口示例

- `POST /api/restaurants/recommend`：推荐餐厅
- `POST /api/restaurants/chat`：餐饮对话
- `POST /api/rag/load` 和 `POST /api/rag/chat`：加载文档并使用 RAG 对话
- `POST /api/streaming/chat`：通过 Server-Sent Events 流式返回
- `POST /api/sentiment/analyze`：分析评论情绪

## 相关文章

- [Spring AI 多模型餐厅推荐实践](https://blog.zhijun.io/posts/spring-ai-restaurant-showcase/)
- [Spring AI 餐厅推荐 RAG 实战](https://blog.zhijun.io/posts/spring-ai-restaurant-showcase-rag/)

## 许可证

本项目采用 Apache License 2.0。完整许可条款请参阅 [LICENSE](LICENSE)。

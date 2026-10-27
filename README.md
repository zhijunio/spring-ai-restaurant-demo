# Spring AI Restaurant Demo

[![Java](https://img.shields.io/badge/Java-21-blue?logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.2-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Spring AI](https://img.shields.io/badge/Spring%20AI-2.0.2-6DB33F?logo=spring&logoColor=white)](https://spring.io/projects/spring-ai)
[![Maven](https://img.shields.io/badge/Maven-3.10.0-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![GitHub stars](https://img.shields.io/github/stars/zhijunio/spring-ai-restaurant-demo)](https://github.com/zhijunio/spring-ai-restaurant-demo/stargazers)
[![License](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](LICENSE)

[简体中文](README.zh-CN.md) | English

A Spring AI sample for restaurant recommendations, conversational dining advice, structured output, and retrieval-augmented generation (RAG). It includes PostgreSQL with pgvector, streaming responses, tool calling, advanced retrieval examples, and sentiment analysis.

## Features

- Restaurant and dish recommendations, dining advice, and chat
- RAG document loading, semantic search, and personalized chat
- Streaming chat and recommendations over Server-Sent Events
- Function calling, reranking, hybrid and multi-query retrieval, and sentiment analysis
- PostgreSQL with pgvector for vector storage

## Requirements

- JDK 21
- [mise](https://mise.jdx.dev/) to install the pinned Java and Maven versions
- Docker Compose
- An OpenAI API key for the default model profile

## Run locally

Install the project toolchain and start PostgreSQL with pgvector:

```bash
mise install
docker compose up -d
```

Set the API key and run the application:

```bash
export OPENAI_API_KEY=your-api-key
./mvnw spring-boot:run
```

Open <http://localhost:8080/>. The Maven profile `open-ai` is active by default. Other configured profiles are `mistral-ai` and `ollama-ai`; see `src/main/resources/application.yml` for the corresponding provider settings.

## API examples

- `POST /api/restaurants/recommend` — recommend restaurants
- `POST /api/restaurants/chat` — restaurant chat
- `POST /api/rag/load` and `POST /api/rag/chat` — load documents and chat with RAG
- `POST /api/streaming/chat` — stream a response using Server-Sent Events
- `POST /api/sentiment/analyze` — analyze a review

## Articles

- [Restaurant recommendations with multiple Spring AI models](https://blog.zhijun.io/posts/spring-ai-restaurant-showcase/)
- [Restaurant recommendations with RAG](https://blog.zhijun.io/posts/spring-ai-restaurant-showcase-rag/)

## License

This project is licensed under the Apache License 2.0. See [LICENSE](LICENSE) for the full terms.

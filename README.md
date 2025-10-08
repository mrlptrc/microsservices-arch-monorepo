# microsservices-arch-monorepo

# 🧠 Microservices Architecture — Spring Boot, Docker, Redis & RabbitMQ

Um projeto de estudo que demonstra uma arquitetura moderna baseada em **microsserviços**, utilizando o ecossistema **Spring Boot**, **Redis**, **RabbitMQ**, **PostgreSQL**, e **Docker**.  
O objetivo é explorar conceitos de **comunicação assíncrona**, **cache**, **mensageria** e **integração contínua (CI/CD)**.

---


📦 **Infraestrutura:**
- **Redis:** Cache e sessões  
- **RabbitMQ:** Comunicação entre serviços  
- **PostgreSQL:** Banco relacional  
- **Docker Compose:** Orquestração local  

---

## 🧰 Tecnologias Utilizadas

| Categoria | Ferramentas |
|------------|--------------|
| Backend | Spring Boot, Spring Web, Spring Data JPA |
| Mensageria | RabbitMQ |
| Cache | Redis |
| Banco de Dados | PostgreSQL |
| Containerização | Docker, Docker Compose |
| CI/CD (futuro) | Jenkins / GitHub Actions |
 

 ## 🧩 Estrutura do Projeto

 microservices-architecture/
├── auth-service/
│   ├── src/
│   ├── pom.xml
│   └── Dockerfile
├── product-service/
├── order-service/
├── payment-service/
├── notification-service/
├── docker-compose.yml
└── README.md

Cada serviço é um projeto Spring Boot independente, com seu próprio application.yml e Dockerfile.



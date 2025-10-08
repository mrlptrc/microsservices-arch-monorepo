# 🧠 Microservices Architecture — Spring Boot, Docker, Redis & RabbitMQ

Um projeto de estudo que demonstra uma arquitetura moderna baseada em **microsserviços**, utilizando o ecossistema **Spring Boot**, **Redis**, **RabbitMQ**, **PostgreSQL**, e **Docker**.

O objetivo é explorar conceitos de **comunicação assíncrona**, **cache**, **mensageria** e **integração contínua (CI/CD)**.

---

## 📦 Infraestrutura

- **Redis:** Cache e sessões
- **RabbitMQ:** Comunicação assíncrona entre serviços
- **PostgreSQL:** Banco de dados relacional
- **Docker Compose:** Orquestração local dos containers

---

## 🧰 Tecnologias Utilizadas

| Categoria          | Ferramentas                              |
|--------------------|------------------------------------------|
| Backend            | Spring Boot, Spring Web, Spring Data JPA|
| Mensageria         | RabbitMQ                                 |
| Cache              | Redis                                    |
| Banco de Dados     | PostgreSQL                               |
| Containerização    | Docker, Docker Compose                   |
| Linguagem          | Java 21                                  |
| Build Tool         | Maven                                    |
| CI/CD (futuro)     | Jenkins / GitHub Actions                 |

---

## 🧩 Estrutura do Projeto

```
microsservices-arch-monorepo/
├── project/                          # Monorepo principal
│   ├── src/main/java/com/microsservices_arch/project/
│   │   ├── core/                     # Módulo compartilhado
│   │   │   ├── config/               # Configurações comuns
│   │   │   ├── dto/                  # DTOs compartilhados
│   │   │   ├── entity/               # Entidades base
│   │   │   ├── exception/            # Exceções globais
│   │   │   └── util/                 # Utilitários comuns
│   │   ├── user/                     # Módulo de usuários
│   │   │   ├── controller/           # REST controllers
│   │   │   ├── service/              # Lógica de negócio
│   │   │   ├── repository/           # Acesso a dados
│   │   │   ├── entity/               # Entidades específicas
│   │   │   └── dto/                  # DTOs específicos
│   │   ├── product/                  # Módulo de produtos
│   │   │   ├── controller/
│   │   │   ├── service/
│   │   │   ├── repository/
│   │   │   ├── entity/
│   │   │   └── dto/
│   │   ├── order/                    # Módulo de pedidos
│   │   │   ├── controller/
│   │   │   ├── service/
│   │   │   ├── repository/
│   │   │   ├── entity/
│   │   │   └── dto/
│   │   └── ProjectApplication.java   # Aplicação principal
│   ├── src/main/resources/
│   │   └── application.properties    # Configurações da aplicação
│   ├── pom.xml                       # Dependências Maven
│   └── Dockerfile                    # Container da aplicação
├── docker-compose.yml                # Orquestração dos serviços
└── README.md
```

**Arquitetura Modular:** Este projeto utiliza uma estrutura de **monorepo modular**, onde cada módulo (`user`, `product`, `order`) representa um domínio de negócio específico, compartilhando infraestrutura comum através do módulo `core`.

---

## 🚀 Como Executar

### Pré-requisitos

- Docker e Docker Compose instalados
- JDK 21+ (para desenvolvimento local)
- Maven 3.8+

### Subindo a aplicação

```bash
# Clone o repositório
git clone <seu-repositorio>
cd microsservices-arch-monorepo

# Suba a infraestrutura com Docker Compose
docker-compose up -d

# Execute a aplicação Spring Boot
cd project
./mvnw spring-boot:run

# Ou compile e execute o JAR
./mvnw clean package
java -jar target/project-0.0.1-SNAPSHOT.jar
```

### Portas dos Serviços

| Serviço           | Porta |
|-------------------|-------|
| Spring Boot App   | 8080  |
| PostgreSQL        | 5432  |
| Redis             | 6379  |
| RabbitMQ AMQP     | 5672  |
| RabbitMQ Management | 15672 |

---

## 📋 Funcionalidades

### 🔐 User Module
- Gerenciamento de usuários
- Autenticação e autorização
- Cache de sessões com Redis

### 🛍️ Product Module  
- CRUD de produtos
- Integração com banco PostgreSQL
- Cache de produtos com Redis

### 📦 Order Module
- Gerenciamento de pedidos
- Publicação de eventos via RabbitMQ
- Integração com módulos de usuário e produto

### 🏗️ Core Module
- Configurações compartilhadas
- DTOs e entidades base
- Tratamento global de exceções
- Utilitários comuns

---

## 🔧 Configuração

### Variáveis de Ambiente

A aplicação utiliza configurações definidas no `application.properties`:

```properties
# Database
spring.datasource.url=jdbc:postgresql://localhost:5432/mydb
spring.datasource.username=postgres
spring.datasource.password=postgres

# Redis
spring.data.redis.host=localhost
spring.data.redis.port=6379

# RabbitMQ
spring.rabbitmq.host=localhost
spring.rabbitmq.port=5672
spring.rabbitmq.username=guest
spring.rabbitmq.password=guest
```

---

## 📚 Conceitos Explorados

- **Arquitetura Modular:** Separação de responsabilidades em módulos independentes
- **Mensageria Assíncrona:** Comunicação entre módulos usando RabbitMQ
- **Cache Distribuído:** Otimização de performance com Redis
- **Containerização:** Isolamento e portabilidade com Docker
- **API REST:** Comunicação HTTP entre clientes e módulos
- **Shared Kernel:** Módulo core com funcionalidades compartilhadas

---

## 🎯 Próximos Passos

- [ ] Implementar API Gateway
- [ ] Adicionar Service Discovery (Eureka)
- [ ] Configurar Circuit Breaker (Resilience4j)
- [ ] Implementar Distributed Tracing (Zipkin/Sleuth)
- [ ] Adicionar testes de integração
- [ ] Configurar pipeline CI/CD
- [ ] Implementar autenticação JWT
- [ ] Adicionar monitoramento com Micrometer/Prometheus
- [ ] Migrar para verdadeira arquitetura de microsserviços separados

---

## 🤝 Contribuição

Este é um projeto de estudo. Sinta-se à vontade para explorar, modificar e aprender com o código!

## 📄 Licença

Este projeto é para fins educacionais.
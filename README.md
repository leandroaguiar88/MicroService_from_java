# 👤 Microservice

Microserviço responsável pelo gerenciamento de usuários dentro de uma arquitetura de **microservices com Spring Cloud**.

Este serviço faz parte de um ecossistema distribuído, integrando com outros serviços como autenticação (OAuth) e API Gateway.

---

## 🚀 Objetivo

Fornecer endpoints para consulta de usuários e seus papéis (roles), permitindo integração com serviços de autenticação e autorização.

---

## 🧠 Arquitetura

Este projeto segue o padrão de microserviços com:

* Service Discovery (Eureka)
* API Gateway (Zuul)
* Comunicação entre serviços (OpenFeign)
* Autenticação centralizada (OAuth2 + JWT)

---

## 🛠️ Tecnologias utilizadas

* Java 11
* Spring Boot 2.3.4.RELEASE
* Spring Cloud (Hoxton.SR12)
* Spring Data JPA
* H2 Database (testes)
* OpenFeign
* Eureka Client
* Maven

---

## 📂 Estrutura do projeto

```
```

* `resources` → configuração da aplicação
* `entities` → entidades (User, Role)
* `repositories` → acesso ao banco de dados
* `services` → regras de negócio
* `resources` → controllers (endpoints REST)

---

## ▶️ Como rodar o projeto

### ✅ Pré-requisitos

* Java 11
* Maven
* Eureka Server rodando (porta 8761)

---

### ▶️ Passos

```bash
# Clonar o repositório
git clone https://github.com/leandroaguiar88/seu-repositorio.git

# Entrar na pasta
Hr config server e o servidor eureka após run nos demais projetos demais independente da ordem

# Rodar o projeto
mvn spring-boot:run
```

---

## 🌐 Configuração importante

No `application.properties`:

```properties
spring.application.name=hr-user

eureka.client.service-url.defaultZone=http://localhost:8761/eureka
```
no caso de utilizar o postman

na subaba Authorization
name = myappleandrolima38
secret = myappsecret1688

na sub aba body
x-www-form-urlencoded
nina@gmail.com
password: 123456
grant_type: password

onde testar o token da aplicação gerada: https://www.jwt.io/


---

## 🔗 Endpoints

### 📌 Buscar usuário por ID

```
GET /users/{id}
```

### 📌 Exemplo de resposta

```json
{
  "id": 1,
  "name": "Maria Brown",
  "email": "maria@gmail.com",
  "roles": [
    {
      "id": 1,
      "roleName": "ROLE_OPERATOR"
    }
  ]
}
```

---

## 🔄 Integração com outros serviços

Este serviço se comunica com:

* **hr-oauth** → autenticação e geração de token JWT
* **API Gateway (Zuul)** → roteamento das requisições
* **Eureka Server** → descoberta de serviços

---

## 🧪 Testes

Você pode testar os endpoints com:

* Postman
* Insomnia

Exemplo:

```
GET http://localhost:8001/users/1
```

---

## 📌 Melhorias futuras

* [ ] Implementar cache com Redis
* [ ] Adicionar testes unitários (JUnit / Mockito)
* [ ] Logging estruturado (ELK)
* [ ] Deploy em cloud (AWS / Docker)

---

## 👨‍💻 Autor

**Leandro de Aguiar Lima**

* GitHub: https://github.com/leandroaguiar88
* LinkedIn: https://linkedin.com/in/leandro-aguiar-329129136/

---

## 📢 Observação

Este projeto foi desenvolvido com foco em aprendizado de arquitetura de microserviços utilizando Spring Boot e Spring Cloud, seguindo boas práticas de separação de responsabilidades e integração entre serviços.

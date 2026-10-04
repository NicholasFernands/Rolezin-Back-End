# Rolezin — Backend

Backend de uma aplicação para **descoberta e gerenciamento de eventos**, permitindo trabalhar com eventos, atrações, locais, avaliações e usuários.

## Objetivo

Construir uma API REST para organizar informações de eventos e seus relacionamentos, utilizando Java, Spring Boot e persistência relacional.

## O que o projeto faz

A API permite:

- Criar, consultar, atualizar e excluir eventos.
- Filtrar eventos por nome e categoria.
- Gerenciar atrações associadas a eventos.
- Gerenciar locais.
- Cadastrar e consultar avaliações.
- Cadastrar usuários e realizar login.

## Tecnologias

- **Java 11**
- **Spring Boot**
- **Spring Web**
- **Spring Data JPA**
- **Hibernate**
- **MySQL**
- **Bean Validation**
- **Lombok**
- **Gradle**
- **JUnit / Spring Boot Test**

## Arquitetura

O projeto é organizado por domínio, separando principalmente `controller`, `model` e `repository`:

```text
src/main/java/com/projeto/rolezin/
├── eventos/
├── atracoes/
├── avaliacoes/
├── locais/
├── usuários/
├── config/
└── utils/
```

O fluxo principal da API é:

```text
HTTP Request
     │
     ▼
Controller
     │
     ▼
Repository
     │
     ▼
JPA / Hibernate
     │
     ▼
MySQL
```

## Modelagem

```text
Usuario
 ├── 1:N ──> Evento
 ├── 1:N ──> Local
 └── 1:N ──> Avaliacao

Evento
 ├── 1:N ──> Atracao
 └── 1:N ──> Avaliacao
```

A modelagem organiza eventos e seus relacionamentos com atrações e avaliações, além das associações com usuários.

## Como clonar

```bash
git clone https://github.com/NickFernands/Rolezin-Back-End.git
cd Rolezin-Back-End
```

## Como executar

Pré-requisitos: **JDK 11** e **MySQL**.

Configure a conexão com o banco em `src/main/resources/application.properties` e execute:

Linux/macOS:

```bash
./gradlew bootRun
```

Windows:

```powershell
.\gradlew.bat bootRun
```

### Testes

```bash
./gradlew test
```

## Observação

Não publique credenciais reais de banco no `application.properties`. Utilize variáveis de ambiente ou outro mecanismo seguro de configuração.

## Autor

**Nicholas Fernandes**

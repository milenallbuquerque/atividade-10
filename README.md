# Atividade 10 - DevOps

## Sobre o projeto

Este projeto foi desenvolvido para aplicar os conhecimentos de DevOps trabalhados durante a atividade.

Foram utilizadas duas APIs:

- Contratos
- Flash Sales

A infraestrutura foi criada utilizando Docker e Docker Compose, com PostgreSQL e Redis para as aplicações.

## Estrutura

O projeto está organizado em duas pastas, uma para cada API:

- Contratos
- Flash Sales

Cada API possui seu próprio Dockerfile, docker-compose.yml e .dockerignore.

Também foi criado um pipeline de CI em `.github/workflows/ci.yml`.

## Tecnologias utilizadas

- Git e GitHub
- Docker
- Docker Compose
- Node.js
- PostgreSQL
- Redis
- GitHub Actions
- Gitleaks

## Como executar

### Contratos

Entrar na pasta:

```bash
cd Contratos
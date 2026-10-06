# Atividade 10 - DevOps

## Sobre o projeto

Este projeto foi desenvolvido para aplicar os conhecimentos de DevOps trabalhados durante o curso.

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

A API fica disponível na porta `3001`.

Para verificar as métricas:

http://localhost:3001/metrics

### Flash Sales

Entrar na pasta:

cd "Flash Sales"

Executar:

docker compose up --build

A API fica disponível na porta `3002`.

Para verificar as métricas:

http://localhost:3002/metrics

Para parar os containers:

docker compose down

## Segurança

Algumas práticas de segurança foram aplicadas no projeto.

As APIs são executadas nos containers utilizando um usuário diferente do root.

Também foi criado o `.gitignore` para evitar o versionamento de arquivos como `node_modules`, arquivos `.env` e logs.

O Gitleaks foi incluído no pipeline para verificar a existência de possíveis segredos no código.

## CI

O arquivo `.github/workflows/ci.yml` possui duas etapas principais:

1. Verificação de segurança com Gitleaks.
2. Build das imagens Docker das duas APIs.

O build das imagens só acontece depois da etapa de segurança.

## Arquitetura

Cada API possui seus próprios serviços de aplicação, PostgreSQL e Redis.

A utilização de containers facilita a configuração do ambiente e permite que os serviços sejam executados de forma isolada.

A separação das duas APIs também facilita futuras alterações ou escalabilidade de cada aplicação.

A separação dos serviços também contribui para a confiabilidade, pois facilita a reprodução do ambiente e reduz o impacto de alterações ou problemas em uma aplicação sobre a outra.

## Git

Foi utilizado Git para versionamento do projeto, com branches para organizar o desenvolvimento.

A branch `main` representa a versão principal e a `develop` é utilizada para integração das alterações.

As funcionalidades são desenvolvidas em branches `feature`.

## Conclusão

Com a infraestrutura criada, as duas APIs podem ser executadas de forma padronizada utilizando Docker.

Além disso, o projeto possui uma etapa automatizada de segurança e build através do GitHub Actions.
# Parthos - Teste Técnico Full Stack

## Introdução
Este projeto é a implementação do teste técnico para desenvolvimento Full Stack, atendendo aos requisitos especificados. O Parthos é um sistema de gerenciamento de tarefas (To-Do List) estruturado em microserviços, utilizando NestJS no backend e React no frontend, com infraestrutura baseada em Docker.

## Funcionalidades Implementadas

### 1. Autenticação de Usuário
- Registro e login de usuários com JWT para autenticação segura.
- Proteção de rotas pelo Proxy.

### 2. Gerenciamento de Tarefas
- Criar, editar, excluir e listar tarefas.
- Marcar tarefas como concluídas.
- Filtragem por status (pendente, concluída).

### 3. Persistência de Dados
- PostgreSQL como banco de dados principal.
- TypeORM para gerência de migrations e models.

### 4. Infraestrutura Dockerizada
- Docker Compose para gerenciar os containers do sistema.
- Nginx como proxy reverso.

## Tecnologias Utilizadas

### Frontend
- Angular
- Material

### Backend
- NestJS
- PostgreSQL
- TypeORM
- JWT para autenticação

### Infraestrutura
- Docker
- Nginx
- CI/CD com GitHub Actions

## Estrutura do Projeto

Os repositórios:

| Nome do Serviço         | Repositório | Porta |
|----------------------|-----------------------------------|-------|
| Parthos Gateway     | https://github.com/Gaiteiro2025/parthos-root.git     | 3000  |
| Parthos Web    | https://github.com/Gaiteiro2025/parthos-web.git    | 8080  |
| Parthos User API    | https://github.com/Gaiteiro2025/parthos-user-api.git    | 3001  |
| Parthos Task API    | https://github.com/Gaiteiro2025/parthos-task-api.git    | 3002  |

```
parthos/
├── docker-compose.yml
├── scripts/
│   ├── setup.sh
├── .env
├── nginx.conf
├── networks/
│   ├── shared-network
├── services/
│   ├── parthos-user-api
│   ├── parthos-task-api
│   ├── parthos-web
│   ├── parthos-gateway
```

## Como Rodar o Projeto

### 1. Clone o Repositório
```sh
mkdir parthos
cd parthos
git clone git@github.com:Gaiteiro2025/parthos-root.git
cd parthos-root
```

### 2. Configure o Ambiente
Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis:
```sh
DB_HOST=db
DB_PORT=5432
DB_USER=postgres
DB_PASS=postgres
DB_NAME=nestdb
HOST=proxy
JWT_SECRET=default_secret
```

### 3. Configure as Permissões do Script
```sh
chmod +x ./scripts/start.dev.sh
```

### 4. Execute o Script de Setup
```sh
./scripts/start.dev.sh
```
Esse script:
- Baixa os Repositorios necessarios
- Configura os containers Docker.
- Inicializa o Nginx como proxy reverso.
- Carrega as variáveis de ambiente automaticamente.

### 5. Inicialização Manual dos Microserviços
Caso prefira iniciar manualmente:
```sh
docker-compose up --build
```

## Testes
### Testes Unitários
```sh
npm run test
```
### Testes de Cobertura
```sh
npm run test:cov
```
### Testes End-to-End
```sh
npm run test:e2e
```
### Testes com Docker
```sh
docker-compose -f docker-compose.test.yml up
```

## CI/CD
O projeto utiliza GitHub Actions para execução automática dos testes a cada commit.

## Licença
Este projeto está sob a licença MIT.


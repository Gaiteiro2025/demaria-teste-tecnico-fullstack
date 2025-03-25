# Parthos - Teste Técnico Full Stack

## Transforme seus problemas em solução

O **Parthos** é uma plataforma de gestão de tarefas projetada para trazer organização e eficiência ao seu dia a dia. Com uma interface responsiva e funcionalidades intuitivas, ele transforma desafios em soluções, ajudando você a manter o foco no que realmente importa.

### Origem do Nome "Parthos"
Inspirado em **Paarthurnax**, de *Skyrim*, **Parthos** simboliza a transformação do caos em ordem e a superação de desafios com sabedoria e foco.

---

## Introdução

Este projeto é a implementação de um teste técnico para desenvolvimento **Full Stack**, atendendo aos requisitos especificados. O **Parthos** é um sistema de gerenciamento de tarefas (*To-Do List*) estruturado em **microserviços**, utilizando **NestJS** no backend e **React** no frontend, com infraestrutura baseada em **Docker**.

### Funcionalidades Implementadas

#### 1. Autenticação de Usuário
- Registro e login de usuários com JWT para autenticação segura.
- Proteção de rotas via Proxy.
- CI/CD configurado com GitHub Actions.

#### 2. Gerenciamento de Tarefas
- Criar, editar, excluir e listar tarefas.
- Marcar tarefas como concluídas.
- Funcionalidade de arrastar tarefas entre colunas.
- Registro de atividades.

#### 3. Persistência de Dados
- **PostgreSQL** como banco de dados principal.
- **TypeORM** para gerenciamento de *migrations* e *models*.

#### 4. Infraestrutura Dockerizada
- **Docker Compose** para gerenciamento dos containers.
- **Nginx** como *proxy* reverso.

#### 5. Releases
- [Frontend](https://github.com/Gaiteiro2025/parthos-web/releases/tag/v1.0.0)
- [User API](https://github.com/Gaiteiro2025/parthos-user-api/releases/tag/v1.0.0)
- [Task API](https://github.com/Gaiteiro2025/parthos-task-api/releases/tag/v1.0.0)

---

## Tecnologias Utilizadas

### Frontend
- Angular
- Material UI

### Backend
- NestJS
- PostgreSQL
- TypeORM
- JWT para autenticação

### Infraestrutura
- Docker
- Nginx
- CI/CD com GitHub Actions

---

## Estrutura do Projeto

### Repositórios

| Serviço            | Repositório | Porta |
|------------------|-----------------------------------|------|
| Parthos Gateway | [Repositório](https://github.com/Gaiteiro2025/parthos-root.git) | 3000  |
| Parthos Web | [Repositório](https://github.com/Gaiteiro2025/parthos-web.git) | 8080  |
| Parthos User API | [Repositório](https://github.com/Gaiteiro2025/parthos-user-api.git) | 3001  |
| Parthos Task API | [Repositório](https://github.com/Gaiteiro2025/parthos-task-api.git) | 3002  |
| Template Parthos | [Repositório](https://github.com/Gaiteiro2025/template-pathos-api.git) | - |

### Estrutura de Pastas

```
parthos-root/
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
```

---

## Como Rodar o Projeto

### 1. Clonar o Repositório
```sh
mkdir parthos
cd parthos
git clone git@github.com:Gaiteiro2025/parthos-root.git
cd parthos-root
```

### 2. Configurar o Ambiente
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

### 3. Configurar Permissões do Script
```sh
chmod +x ./scripts/start.dev.sh
```

### 4. Executar o Script de Setup
```sh
./scripts/start.dev.sh
```
Esse script:
- Baixa os repositórios necessários.
- Configura os containers Docker.
- Inicializa o Nginx como proxy reverso.
- Carrega as variáveis de ambiente automaticamente.

### 5. Inicialização Manual dos Microserviços
Caso prefira iniciar manualmente:
```sh
docker-compose up --build
```

---

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

---

## CI/CD
O projeto utiliza **GitHub Actions** para execução automática de testes a cada commit.

---

## Licença
Este projeto está sob a **licença MIT**.


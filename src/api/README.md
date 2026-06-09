# 🤖 Backend API — NestJS

## Visão Geral

API REST do EcoFit construída com NestJS e PostgreSQL.

## Estrutura

- **src/auth/** - Módulo de autenticação (JWT, OAuth)
- **src/users/** - Módulo de usuários
- **src/workouts/** - Módulo de treinos
- **src/habits/** - Módulo de hábitos
- **src/chat/** - Módulo CapyCoach (integração IA)
- **src/database/** - Configuração Prisma
- **src/main.ts** - Ponto de entrada
- **prisma/schema.prisma** - Schema do banco
- **test/** - Testes (unit + E2E)

## Tecnologias

- NestJS
- TypeScript
- Prisma ORM
- PostgreSQL (Supabase)
- JWT Auth
- OpenAI (CapyCoach)

## Rodando

```bash
npm install
npm run dev
```

## Estrutura de Módulos

```
src/
├── auth/
│   ├── auth.module.ts
│   ├── auth.service.ts
│   ├── auth.controller.ts
│   └── guards/
├── users/
│   ├── users.module.ts
│   ├── users.service.ts
│   ├── users.controller.ts
│   └── dto/
├── workouts/
├── habits/
├── chat/
│   ├── chat.module.ts
│   ├── chat.service.ts (OpenAI integration)
│   └── chat.controller.ts
└── database/
    └── prisma.service.ts
```

## Endpoints Principais

```
POST   /auth/login              → Login
POST   /auth/register           → Registrar
GET    /users/:id               → Perfil
POST   /workouts                → Criar treino
GET    /workouts                → Listar treinos
POST   /chat                    → Enviar mensagem CapyCoach
GET    /habits                  → Listar hábitos
```

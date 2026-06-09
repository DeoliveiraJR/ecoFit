# 🏗️ Arquitetura EcoFit — Estrutura Completa

```
ecoFit/ (repositório GitHub)
│
├── .github/
│   └── skills/                          ← Documentação para agentes IA
│       ├── ecofit-design/SKILL.md       (colors, typography, components)
│       ├── ecofit-development/SKILL.md  (git workflow, commits)
│       └── ecofit-getting-started/SKILL.md (setup, stack, roadmap)
│
├── src/
│   │
│   ├── mobile/                          ← React Native + Expo
│   │   ├── app/                         (Expo Router pages)
│   │   │   ├── index.tsx                (Splash)
│   │   │   ├── (auth)/                  (Login, Onboarding, Register)
│   │   │   │   ├── login.tsx
│   │   │   │   ├── onboarding.tsx
│   │   │   │   └── register.tsx
│   │   │   └── (app)/                   (Main app screens)
│   │   │       ├── home.tsx
│   │   │       ├── chat.tsx
│   │   │       ├── workouts.tsx
│   │   │       ├── habits.tsx
│   │   │       ├── massage.tsx
│   │   │       └── profile.tsx
│   │   ├── components/                  (Reusable UI - Button, Card, Input, Nav)
│   │   ├── screens/                     (Page/screen components)
│   │   ├── hooks/                       (Custom React hooks)
│   │   ├── services/                    (API calls, external services)
│   │   ├── stores/                      (State management - Zustand/Context)
│   │   ├── styles/                      (Global styles, theme)
│   │   ├── types/                       (TypeScript interfaces)
│   │   ├── package.json                 (Dependencies)
│   │   ├── app.json                     (Expo config)
│   │   └── README.md                    (Setup mobile)
│   │
│   ├── api/                             ← NestJS Backend + Prisma
│   │   ├── src/
│   │   │   ├── auth/                    (JWT, OAuth, guards)
│   │   │   │   ├── auth.module.ts
│   │   │   │   ├── auth.service.ts
│   │   │   │   ├── auth.controller.ts
│   │   │   │   └── guards/
│   │   │   │
│   │   │   ├── users/                   (User management)
│   │   │   │   ├── users.module.ts
│   │   │   │   ├── users.service.ts
│   │   │   │   ├── users.controller.ts
│   │   │   │   └── dto/
│   │   │   │
│   │   │   ├── workouts/                (Workout tracking)
│   │   │   │   ├── workouts.module.ts
│   │   │   │   ├── workouts.service.ts
│   │   │   │   ├── workouts.controller.ts
│   │   │   │   └── dto/
│   │   │   │
│   │   │   ├── habits/                  (Habit tracking)
│   │   │   │   ├── habits.module.ts
│   │   │   │   ├── habits.service.ts
│   │   │   │   ├── habits.controller.ts
│   │   │   │   └── dto/
│   │   │   │
│   │   │   ├── chat/                    (CapyCoach IA)
│   │   │   │   ├── chat.module.ts
│   │   │   │   ├── chat.service.ts      (OpenAI integration)
│   │   │   │   ├── chat.controller.ts
│   │   │   │   └── dto/
│   │   │   │
│   │   │   ├── database/
│   │   │   │   └── prisma.service.ts    (Prisma connection)
│   │   │   │
│   │   │   └── main.ts                  (Entry point)
│   │   │
│   │   ├── prisma/
│   │   │   └── schema.prisma            (Database schema)
│   │   │
│   │   ├── test/                        (Unit + E2E tests)
│   │   ├── package.json                 (Dependencies)
│   │   ├── tsconfig.json                (TypeScript config)
│   │   └── README.md                    (Setup API)
│   │
│   └── shared/                          ← Código compartilhado
│       ├── types/                       (User, Workout, Habit, Chat)
│       ├── constants/                   (API URLs, messages)
│       ├── utils/                       (Formatting, validation, date)
│       └── README.md
│
├── .gitignore
├── README.md                            ← Visão geral
├── CHANGELOG.md                         ← Version history
└── package.json                         ← Monorepo root (opcional)
```

---

## 📊 Stateless vs Backend Services

### Frontend (mobile/)
```
React Native App → NativeWind (Tailwind)
   ↓
[components/] + [screens/]
   ↓
[services/] → API calls → https://api.ecofit.com
   ↓
[stores/] → State Management (Zustand)
```

### Backend (api/)
```
NestJS Server (port 3000)
   ↓
[auth/] → JWT, OAuth, Guards
   ↓
[users/, workouts/, habits/, chat/] → Business Logic
   ↓
[database/] + Prisma → PostgreSQL (Supabase)
   ↓
Services → OpenAI (CapyCoach)
```

### Shared (shared/)
```
TS Interfaces + Constants
   ↓
Usados em mobile/ E api/
```

---

## 🔄 Fluxo de Dados

1. **Mobile** → User action (ex: click "Iniciar Treino")
2. **Service** → POST /workouts → API
3. **API Auth** → Valida JWT
4. **Workout Module** → Salva no DB via Prisma
5. **Response** → Volta para mobile
6. **Store** → Atualiza state (Zustand)
7. **Screen** → Re-render com dados novos

---

## 🎯 Próximos Passos

1. **Configurar package.json** em mobile/ e api/
2. **Instalar dependências:**
   ```bash
   cd src/mobile && npm install
   cd ../api && npm install
   ```
3. **Configurar .env** com URLs de API e Supabase
4. **Iniciar desenvolvimento:**
   - Mobile: `npm run dev` (Expo)
   - API: `npm run dev` (NestJS)
5. **Criar primeiros componentes e endpoints**

---

## 📁 Checklist de Criação

- ✅ Estrutura de diretórios criada
- ✅ README em cada módulo principal
- ✅ .gitkeep em pastas vazias
- 📋 package.json em mobile/ e api/
- 📋 tsconfig.json em api/
- 📋 app.json em mobile/ (Expo config)
- 📋 prisma/schema.prisma (database design)
- 📋 .env.example para variáveis

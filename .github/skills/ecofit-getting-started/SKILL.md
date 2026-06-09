# EcoFit Getting Started — Setup, Arquitetura e Stack

**Versão:** 1.0.0  
**Scope:** Onboarding, setup inicial, stack técnico, arquitetura, roadmap  
**Mantido por:** Equipe de Arquitetura

---

## 🎯 O que é EcoFit?

**EcoFit** é um aplicativo mobile de saúde, bem-estar e acompanhamento de hábitos voltado exclusivamente para o setor ECOA.

**Objetivo:** Melhorar qualidade de vida através de:
- 📊 Rastreamento de treinamentos
- 💧 Hidratação e sono
- 🎯 Metas e objetivos
- 💆 Agendamento de massoterapia
- 🤖 CapyCoach (assistente IA conversacional)

**Público:** Funcionários e associados do setor ECOA

---

## 🦫 Mascote: CapyCoach

Uma capivara atleta, nerd com óculos, energética e motivadora.

**Personalidade:**
- Motivadora e amigável
- Oferece dicas de bem-estar
- Guia o usuário pelo app
- Personagem memorável e diferenciador

---

## 🛠️ Stack Técnico

### Frontend Mobile

| Tecnologia | Versão | Uso |
|------------|--------|-----|
| **React Native** | Latest | Framework mobile |
| **Expo** | Latest | Tooling e builds |
| **Expo Router** | Latest | Roteamento |
| **NativeWind** | Latest | Estilização (Tailwind para RN) |
| **TypeScript** | Latest | Type safety |

### Backend

| Tecnologia | Versão | Uso |
|------------|--------|-----|
| **NestJS** | Latest | Framework Node.js |
| **TypeScript** | Latest | Type safety |
| **Prisma** | Latest | ORM |
| **PostgreSQL** | Latest | Database (via Supabase) |

### Serviços Externos

| Serviço | Uso |
|---------|-----|
| **Supabase** | PostgreSQL database + Auth |
| **Agno** | Framework IA |
| **OpenAI** | LLM para CapyCoach |
| **Render** | Deploy backend |

### Design

| Tecnologia | Uso |
|------------|-----|
| **Figma** | Design system + prototypes |
| **NativeWind** | Implementar design em código |

---

## 📁 Estrutura de Repositório

```
ecoFit/ (GitHub: DeoliveiraJR/ecoFit)
├── .github/
│   └── skills/
│       ├── ecofit-design/SKILL.md          ← Design system
│       ├── ecofit-development/SKILL.md     ← Git workflow
│       └── ecofit-getting-started/SKILL.md ← Este arquivo
├── src/
│   ├── mobile/          ← React Native app
│   ├── api/             ← NestJS backend
│   └── shared/          ← Código compartilhado
├── README.md            ← Visão geral do projeto
├── CHANGELOG.md         ← Histórico de versões
└── .gitignore
```

---

## 🚀 Roadmap (7 Fases)

### Fase 0: Foundation (Atual)
- ✅ Figma design system
- ✅ Tech stack definido
- ✅ Repositório iniciado
- 🔄 Setup local (in progress)

### Fase 1: MVP Core
- Autenticação básica
- Home dashboard
- Rastreamento de treinos
- Visualização de hábitos

### Fase 2: CapyCoach MVP
- Chat básico
- Respostas pré-definidas
- Integração OpenAI

### Fase 3: Funcionalidades Avançadas
- Agendamento massoterapia
- Histórico de treinos
- Metas customizáveis

### Fase 4: Polish & Performance
- Testes (unit + E2E)
- Otimizações
- Acessibilidade

### Fase 5: Beta Release
- Deploy em produção
- Feedback de usuários
- Ajustes baseados em usage

### Fase 6: Analytics & Growth
- Tracking de comportamento
- Features beta
- Expansão de funcionalidades

### Fase 7: Scale
- Múltiplos idiomas
- Sync offline
- Marketplace de trainers

---

## 💻 Setup Inicial

### 1. Clone o Repositório

```bash
git clone https://github.com/DeoliveiraJR/ecoFit.git
cd ecoFit
```

### 2. Instalar Dependências

```bash
# Frontend
cd src/mobile
npm install
# ou
yarn install

# Backend
cd ../api
npm install
```

### 3. Configurar Variáveis de Ambiente

```bash
# .env.local (mobile)
EXPO_PUBLIC_API_URL=http://localhost:3000
EXPO_PUBLIC_SUPABASE_URL=...
EXPO_PUBLIC_SUPABASE_KEY=...

# .env (backend)
DATABASE_URL=postgresql://...
OPENAI_API_KEY=...
JWT_SECRET=...
```

### 4. Rodar Localmente

```bash
# Frontend (Expo)
cd src/mobile
npm run dev
# Abrir em: http://localhost:8081

# Backend (NestJS)
cd src/api
npm run dev
# API em: http://localhost:3000
```

---

## 📊 Arquitetura

> 📖 **Para estrutura completa de diretórios, diagrama de fluxo de dados e integração mobile↔api**, consulte:
> 
> ### 🔗 [ARCHITECTURE.md](../../ARCHITECTURE.md) ← **REFERÊNCIA OFICIAL**
> 
> Você encontrará:
> - ✅ Estrutura completa `src/mobile/` com todas as pastas
> - ✅ Estrutura completa `src/api/` com todos os módulos
> - ✅ Estrutura `src/shared/` com tipos e utilitários compartilhados
> - ✅ Fluxo de dados: User Action → Frontend Service → API → Database → Response
> - ✅ Checklist de criação (package.json, tsconfig.json, app.json, schema.prisma, etc)
> - ✅ Exemplos de uso e boas práticas

---

## 🔑 Principais Conceitos

### Database Schema (Preview)

```sql
-- Users
CREATE TABLE users (
  id UUID PRIMARY KEY,
  email VARCHAR UNIQUE,
  name VARCHAR,
  avatar_url VARCHAR,
  created_at TIMESTAMP
);

-- Workouts
CREATE TABLE workouts (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users,
  name VARCHAR,
  date TIMESTAMP,
  duration INT
);

-- Habits
CREATE TABLE habits (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users,
  name VARCHAR,
  frequency VARCHAR, -- daily, weekly
  completion_status BOOLEAN,
  created_at TIMESTAMP
);

-- Chat Messages
CREATE TABLE chat_messages (
  id UUID PRIMARY KEY,
  user_id UUID REFERENCES users,
  content TEXT,
  role VARCHAR, -- user, assistant
  created_at TIMESTAMP
);
```

### API Endpoints (Exemplo)

```
GET    /api/auth/me              → Current user
POST   /api/auth/login           → Login
POST   /api/auth/register        → Register
GET    /api/users/:id            → User profile
POST   /api/workouts             → Create workout
GET    /api/workouts             → List workouts
POST   /api/chat                 → Send message
GET    /api/habits               → List habits
POST   /api/massotherapy/book    → Book appointment
```

---

## 📱 11 Telas do MVP

1. **Splash** - Tela inicial com logo
2. **Onboarding** - Welcome flow
3. **Login** - Autenticação
4. **Home** - Dashboard principal
5. **Chat CapyCoach** - Conversa IA
6. **Treinos** - Lista de workouts
7. **Exercício** - Detalhe de workout
8. **Hábitos** - Rastreamento de hábitos
9. **Massoterapia** - Agendamento
10. **Perfil** - Configurações de usuário
11. **Mais** - Menu adicional

*Design em Figma:* https://figma.com/design/V2QRBuCzkJCFKEYYBs76nJ

---

## ✅ Checklist de Setup

- [ ] Clone do repositório feito
- [ ] Dependências instaladas (npm install)
- [ ] Variáveis de ambiente configuradas
- [ ] Database conectada (Supabase)
- [ ] Frontend rodando (Expo)
- [ ] Backend rodando (NestJS)
- [ ] Consegue abrir app no simulator/device

---

## 📚 Recursos Úteis

| Recurso | Link |
|---------|------|
| Documentação React Native | [reactnative.dev](https://reactnative.dev) |
| Expo | [expo.dev](https://expo.dev) |
| NestJS | [nestjs.com](https://nestjs.com) |
| Prisma | [prisma.io](https://prisma.io) |
| Supabase | [supabase.com](https://supabase.com) |
| Figma Design | [figma.com/.../V2QRBuCzkJCFKEYYBs76nJ](https://figma.com/design/V2QRBuCzkJCFKEYYBs76nJ) |

---

## 🤝 Contribuindo

1. Crie uma branch: `git checkout -b feature/sua-feature`
2. Faça commits: `git commit -m "feat: descrição"`
3. Faça push: `git push origin feature/sua-feature`
4. Abra um Pull Request em `main`
5. Aguarde revisão e merge

*Veja [ecofit-development](../ecofit-development/SKILL.md) para detalhes de workflow.*

---

## 🚀 Próximos Passos

1. Setup local conforme acima
2. Criar primeira branch de feature
3. Implementar autenticação
4. Conectar ao Supabase
5. Criar screens básicas
6. Testar no simulator

---

## 📞 Suporte

Para dúvidas ou problemas:
- Consulte a [documentação do projeto](../../README.md)
- Verifique o [CHANGELOG](../../CHANGELOG.md)
- Revise a skill de [desenvolvimento](../ecofit-development/SKILL.md)
- Abra uma issue no GitHub

**Repository:** https://github.com/DeoliveiraJR/ecoFit

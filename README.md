# EcoFit

> Saúde, bem-estar e acompanhamento de hábitos para o setor ECOA, com assistente IA personificado.

---

## 🎯 Visão Geral

**EcoFit** é um aplicativo mobile que promove qualidade de vida através de:

- 📊 **Rastreamento de Treinos** - Registre e acompanhe seus workouts
- 💧 **Hábitos Saudáveis** - Hidratação, sono, alimentação
- 🎯 **Metas Personalizadas** - Defina e conquiste objetivos
- 💆 **Agendamento de Massoterapia** - Marque sessões facilmente
- 🤖 **CapyCoach (IA)** - Assistente conversacional motivador

**Público:** Funcionários e associados do setor ECOA

---

## 🦫 CapyCoach

Mascote exclusivo: uma capivara atleta, nerd com óculos, energética e motivadora. Guia os usuários através de toda experiência do app com dicas de bem-estar e motivação.

---

## 📱 11 Telas do MVP

| Tela | Descrição |
|------|-----------|
| 1. Splash | Logo e animação de abertura |
| 2. Onboarding | Boas-vindas e introdução |
| 3. Login | Autenticação e OAuth |
| 4. **Home** | Dashboard com métricas e agenda |
| 5. Chat CapyCoach | Interface conversacional IA |
| 6. Treinos | Lista de workouts |
| 7. Exercício | Detalhe de treino com vídeo |
| 8. Hábitos | Rastreamento de hábitos diários |
| 9. Massoterapia | Agendamento de sessões |
| 10. Perfil | Configurações e dados do usuário |
| 11. Mais | Menu com opções adicionais |

**Design:** [Figma - EcoFit MVP](https://figma.com/design/V2QRBuCzkJCFKEYYBs76nJ)

---

## 🛠️ Stack Técnico

### Frontend Mobile
- **React Native** - Framework mobile cross-platform
- **Expo** - Tooling e build system
- **Expo Router** - Roteamento e navegação
- **NativeWind** - Styling (Tailwind para React Native)
- **TypeScript** - Type safety

### Backend
- **NestJS** - Framework Node.js robusto
- **TypeScript** - Type safety
- **Prisma ORM** - Acesso a banco de dados
- **PostgreSQL** - Via Supabase

### Serviços
- **Supabase** - Database PostgreSQL + Auth
- **Agno** - Framework de IA
- **OpenAI** - LLM para CapyCoach
- **Render** - Deploy backend

---

## 📁 Estrutura de Projeto

```
ecoFit/
├── .github/
│   └── skills/
│       ├── ecofit-design/            ← Design System & Figma
│       ├── ecofit-development/       ← Git Workflow & Development
│       └── ecofit-getting-started/   ← Setup & Arquitetura
├── src/
│   ├── mobile/      ← React Native App
│   ├── api/         ← NestJS Backend
│   └── shared/      ← Código compartilhado
├── README.md        ← Este arquivo
└── CHANGELOG.md     ← Histórico de versões
```

---

## 🚀 Roadmap (7 Fases)

| Fase | Nome | Status | Duração |
|------|------|--------|---------|
| 0 | **Foundation** | 🔄 In Progress | Semanas 1-2 |
| 1 | MVP Core | 📋 Planned | Semanas 3-6 |
| 2 | CapyCoach MVP | 📋 Planned | Semanas 7-9 |
| 3 | Funcionalidades Avançadas | 📋 Planned | Semanas 10-12 |
| 4 | Polish & Performance | 📋 Planned | Semanas 13-14 |
| 5 | Beta Release | 📋 Planned | Semanas 15-16 |
| 6 | Analytics & Growth | 📋 Planned | Contínuo |
| 7 | Scale | 📋 Planned | Contínuo |

---

## 📚 Documentação

- **[Getting Started](.github/skills/ecofit-getting-started/SKILL.md)** - Setup inicial, stack, arquitetura
- **[Design System](.github/skills/ecofit-design/SKILL.md)** - Cores, tipografia, componentes, Figma
- **[Development Workflow](.github/skills/ecofit-development/SKILL.md)** - Git, commits, branches, push/pull
- **[CHANGELOG](./CHANGELOG.md)** - Histórico de versões

---

## ⚡ Quick Start

```bash
# 1. Clone
git clone https://github.com/DeoliveiraJR/ecoFit.git
cd ecoFit

# 2. Instale dependências
cd src/mobile && npm install
cd ../api && npm install

# 3. Configure .env
# Veja Getting Started para detalhes

# 4. Rode localmente
# Frontend (Mobile)
cd src/mobile && npm run dev

# Backend (API)
cd src/api && npm run dev
```

Para instruções completas, veja [Getting Started](.github/skills/ecofit-getting-started/SKILL.md).

---

## 🤝 Contribuindo

1. Crie uma branch: `git checkout -b feature/sua-feature`
2. Faça commits: `git commit -m "feat: descrição"`
3. Faça push: `git push origin feature/sua-feature`
4. Abra um Pull Request para `main`

Veja [Development Workflow](.github/skills/ecofit-development/SKILL.md) para mais detalhes.

---

## 📊 Status

- ✅ Design System (Figma)
- ✅ Arquitetura definida
- ✅ Stack técnico escolhido
- 🔄 Setup inicial
- 📋 Implementação MVP

---

## 📞 Links

- **GitHub:** https://github.com/DeoliveiraJR/ecoFit
- **Figma Design:** https://figma.com/design/V2QRBuCzkJCFKEYYBs76nJ
- **Supabase Dashboard:** https://app.supabase.com
- **Render Deploy:** https://render.com

---

## 📝 Licença

MIT - Projeto EcoFit © 2026

- Agenda
- Reservas

### Fase 6

CapyCoach

- Chat
- Contexto
- Tool Calling

### Fase 7

Deploy

- Render
- Produção

---

## Checklist Mestre

### Fundação

- [ ] Monorepo
- [ ] Expo
- [ ] NestJS
- [ ] Prisma
- [ ] Supabase

### Autenticação

- [ ] Google Login
- [ ] Microsoft Login

### Perfil

- [ ] Peso
- [ ] Altura
- [ ] Objetivos

### Treinos

- [ ] Exercícios
- [ ] Séries
- [ ] Histórico

### Hábitos

- [ ] Água
- [ ] Sono
- [ ] Alimentação

### Massoterapia

- [ ] Agenda
- [ ] Reservas
- [ ] Cancelamentos

### IA

- [ ] CapyCoach
- [ ] Tool Calling

### Produção

- [ ] Render
- [ ] Monitoramento
- [ ] Backup

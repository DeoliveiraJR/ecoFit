# 🔧 Mantendo ARCHITECTURE.md Atualizado

**Versão:** 1.0.0  
**Scope:** Manutenção de documentação de arquitetura  
**Responsável:** Equipe de Desenvolvimento  
**Frequência:** Sempre que estrutura ou módulos mudar

---

## 📋 Quando Atualizar ARCHITECTURE.md

Você DEVE atualizar `ARCHITECTURE.md` quando:

### ✅ Estrutura de Diretórios
- Criar novo diretório em `src/mobile/`, `src/api/` ou `src/shared/`
- Deletar diretório existente
- Reorganizar pastas (mover módulos de lugar)
- Renomear pastas ou módulos

**Exemplo:** 
```bash
# Você criou
mkdir -p src/api/src/notifications/

# ENTÃO você deve atualizar ARCHITECTURE.md adicionando:
# notifications/              (Notificações)
# ├── notifications.module.ts
# └── notifications.service.ts
```

### ✅ Módulos e Serviços
- Adicionar novo módulo NestJS (ex: `notifications`, `analytics`)
- Remover módulo existente
- Alterar responsabilidade de módulo

**Exemplo:**
```bash
# Você criou services para Analytics
# ENTÃO você adiciona à seção de api:
# ├── analytics/              (Google Analytics, eventos)
# │   ├── analytics.module.ts
# │   ├── analytics.service.ts
```

### ✅ Componentes React Native
- Criar novo componente reutilizável importante (ex: `FormField`, `LoadingSpinner`)
- Deletar componentes
- Alterar estrutura de `components/`

### ✅ Data Flow ou Integração
- Mudar como frontend se comunica com backend
- Adicionar novo serviço externo (API, SDK)
- Alterar pipeline de processamento de dados

**Exemplo:**
```bash
# Você integrou com Stripe
# ENTÃO você atualiza o diagrama de fluxo de dados em ARCHITECTURE.md:
# Frontend Request → Stripe Service → NestJS API → Database
```

### ✅ Banco de Dados
- Adicionar nova tabela em `prisma/schema.prisma`
- Remover tabela
- Alterar relacionamentos principais

---

## 🔄 Como Atualizar ARCHITECTURE.md

### 1. Abrir Arquivo

```bash
cd /c/Users/morai/Desktop/devoJR/freelas/ecoFIT/ecoFit
vim ARCHITECTURE.md
# ou use um editor visual
```

### 2. Localizar Seção Correta

ARCHITECTURE.md tem estrutura:
```
🏗️ Arquitetura EcoFit — Estrutura Completa
├── ecoFit/ (repositório)
│   ├── .github/
│   ├── src/
│   │   ├── mobile/         ← Atualizar aqui se mudança em mobile
│   │   ├── api/            ← Atualizar aqui se mudança em api
│   │   └── shared/         ← Atualizar aqui se mudança em shared
│   └── ...
├── 📊 Fluxo de Dados       ← Atualizar para mudanças em integração
├── ✅ Checklist de Criação ← Atualizar quando criar arquivos novos
└── 🔗 Referências
```

### 3. Manter Formato Consistente

**Sempre use este padrão:**

```
# Para diretórios
│   ├── nova-pasta/                  (Descrição breve)
│   │   ├── arquivo1.ts              (O que faz)
│   │   └── arquivo2.ts              (O que faz)

# Para comentários de estrutura
(DescriçãoDoMódulo com emojis conforme padrão)
```

**Padrão de emojis já usado:**
- 📱 Mobile/Frontend
- 🤖 Backend/APIs
- 🔐 Autenticação
- 👤 Usuários
- 🏋️ Workouts/Treinos
- 🎯 Hábitos/Goals
- 💬 Chat/Comunicação
- 🗄️ Database

### 4. Atualizar Checklist

Se criar arquivo novo, adicione ao final em `✅ Checklist de Criação`:

```markdown
✅ Checklist de Criação

✅ Estrutura de diretórios (.gitkeep)
✅ README.md em src/mobile/ e src/api/
✅ .gitignore
✅ ARCHITECTURE.md
✅ ARCHITECTURE_MAINTENANCE.md (Este arquivo)
- [ ] package.json em src/mobile/
- [ ] package.json em src/api/
...
✅ novoCriado/arquivo.ts
```

### 5. Testar Consistência

Depois de editar:

```bash
# Ver o arquivo
cat ARCHITECTURE.md | head -100

# Verificar indentação (deve estar alinhada)
# Verificar emojis (devem estar presentes)
# Verificar links (devem apontar para arquivos corretos)
```

---

## 📝 Exemplo Prático: Adicionar Novo Módulo

**Cenário:** Você criou `src/api/src/notifications/` para notificações.

### Passo 1: Editar ARCHITECTURE.md

Encontre a seção de `src/api/src/`:

```markdown
│   ├── src/
│   │   ├── auth/
│   │   ├── users/
│   │   ├── workouts/
│   │   ├── habits/
│   │   ├── chat/
```

Adicione antes de `database/`:

```markdown
│   │   ├── notifications/           🔔 Notificações (push, email)
│   │   │   ├── notifications.module.ts
│   │   │   ├── notifications.service.ts
│   │   │   ├── notifications.controller.ts
│   │   │   └── templates/           (Templates de email/SMS)
```

### Passo 2: Atualizar Fluxo de Dados (se aplicável)

Se usar serviço externo (ex: SendGrid):

```markdown
### 📊 Fluxo de Dados

#### Enviar Notificação
Frontend Action (evento de conclusão de workout)
↓
Mobile Service → api/notifications/sendNotification()
↓
NestJS Controller → NotificationsService
↓
SendGrid API
↓
Email/SMS para usuário
```

### Passo 3: Atualizar Checklist

```markdown
✅ notifications/                         (Novo módulo criado)
   ✅ notifications.module.ts
   ✅ notifications.service.ts
   ✅ notifications.controller.ts
   - [ ] Testes unitários
```

### Passo 4: Commitar

```bash
git add ARCHITECTURE.md
git commit -m "docs: adicionar módulo notifications ao ARCHITECTURE.md"
git push origin main
```

---

## 🔗 Ligação com CHANGELOG.md

Sempre que atualizar ARCHITECTURE.md, **também atualize CHANGELOG.md**:

```markdown
## v1.2.0 (Data)

### 🏗️ Arquitetura
- Adicionar módulo de notificações
- Atualizar diagrama de fluxo de dados

### 📝 Documentação
- Atualizar ARCHITECTURE.md com novo módulo
```

**Comando:**

```bash
# Editar CHANGELOG.md adicionando a mudança
vim CHANGELOG.md

# Commitar junto
git add ARCHITECTURE.md CHANGELOG.md
git commit -m "docs: adicionar módulo notifications e atualizar ARCHITECTURE + CHANGELOG"
git push origin main
```

---

## ✅ Checklist de Atualização

Antes de fazer push com mudanças em ARCHITECTURE.md:

- [ ] Estrutura de diretórios está correta?
- [ ] Indentação usa `│` e `├──/└──` corretamente?
- [ ] Descrições estão em português?
- [ ] Emojis estão presentes e consistentes?
- [ ] Checklist final foi atualizado?
- [ ] Fluxo de dados foi atualizado (se estrutural)?
- [ ] CHANGELOG.md também foi atualizado?
- [ ] Executei `git status` e revisei alterações?
- [ ] Mensagem de commit é clara?

---

## 🚀 Ferramentas Úteis

### Visualizar diferenças
```bash
git diff ARCHITECTURE.md
```

### Ver histórico de mudanças neste arquivo
```bash
git log --follow -p ARCHITECTURE.md
```

### Reverter para última versão se cometer erro
```bash
git restore ARCHITECTURE.md
```

---

## 📞 Quando Pedir Ajuda

Se você não tem certeza sobre:

1. **Onde colocar novo código?**  
   → Consulte [ARCHITECTURE.md](./ARCHITECTURE.md)

2. **Como estruturar novo módulo?**  
   → Procure padrão similar em `src/api/src/users/` ou `src/api/src/workouts/`

3. **Preciso mover código de pasta?**  
   → Faça o move, depois **atualize ARCHITECTURE.md** e inclua no commit

4. **Não sei se devo atualizar ARCHITECTURE.md?**  
   → Quando em dúvida: **ATUALIZE!** É melhor documentar extra do que deixar desatualizado.

---

## 📚 Documentos Relacionados

- [ARCHITECTURE.md](./ARCHITECTURE.md) — Estrutura completa
- [README.md](./README.md) — Visão geral do projeto
- [CHANGELOG.md](./CHANGELOG.md) — Histórico de versões
- [.github/skills/ecofit-getting-started/SKILL.md](./.github/skills/ecofit-getting-started/SKILL.md) — Setup e onboarding
- [.github/skills/ecofit-development/SKILL.md](./.github/skills/ecofit-development/SKILL.md) — Workflow Git


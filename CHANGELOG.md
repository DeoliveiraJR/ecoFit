# Changelog

Todas as mudanças relevantes do projeto serão registradas aqui.

---

## [1.1.0] - Reestruturação & Simplificação

**Data:** 2026-06-09

### Mudanças Estruturais

- ✅ Removido worktree `agents-figma-projeto-criacao`
- ✅ Deletada branch remota `agents/figma-projeto-criacao`
- ✅ Simplificado para repositório **uma única branch: `main`**
- ✅ Criada estrutura de skills modular e documentada

### Skills Criadas

#### `.github/skills/ecofit-design/SKILL.md`
- Design System completo (cores, tipografia, componentes)
- Paleta de 9 cores com hex/RGB
- Especificações de componentes (Button, Card, Input, Navigation)
- Mascote CapyCoach (uso e dimensões)
- Referência Figma com 11 screens
- Design tokens em CSS variables

#### `.github/skills/ecofit-development/SKILL.md`
- Workflow padrão: commit → push em `main`
- Fluxo avançado: feature branches temporárias
- Tipos de commit (feat, fix, docs, design, etc)
- Sincronização com remoto
- Desfazer commits, conflitos, revert
- Checklist antes de push

#### `.github/skills/ecofit-getting-started/SKILL.md`
- Visão geral do projeto EcoFit
- Stack técnico completo
- Estrutura de repositório
- 7 fases do roadmap
- Setup inicial (clone, instalar, configurar, rodar)
- Arquitetura (Mobile + Backend)
- Database schema preview
- 11 telas do MVP
- Checklist de setup

### Atualizações de Documentação

#### README.md
- Reformatado com emojis e melhor legibilidade
- Adicionadas seções de links para skills
- Tabela das 11 telas com descrições
- Stack técnico com detalhes
- Links diretos para Figma, Supabase, Render
- Quick Start simplificado

#### CHANGELOG.md
- Adicionada seção v1.1.0
- Documentadas todas as mudanças estruturais

### Benefícios

✨ **Clareza:** Estrutura simples (main only, sem worktrees confusos)  
📚 **Documentação:** Skills modulares por propósito (design, dev, setup)  
🔄 **Workflow:** Fluxo padronizado para commits e branches  
🤖 **IA-Ready:** Skills consultáveis por agentes de desenvolvimento  

### Próximas Etapas

- [ ] Implementar fase 1: MVP Core (autenticação, home, treinos, hábitos)
- [ ] Setup inicial em máquina local
- [ ] Criar primeira feature branch
- [ ] Conectar ao Supabase
- [ ] Testes iniciais no simulator

---

## [1.0.0] - Fundação do Projeto

### Definido

- Nome oficial: EcoFit
- Mascote oficial: CapyCoach
- Aplicação exclusiva para ECOA
- MVP definido

### Arquitetura

- React Native
- Expo
- NestJS
- Supabase
- Prisma
- Agno
- OpenAI
- Render

### UX

- Home
- Chat
- Treinos
- Hábitos
- Massoterapia
- Perfil

### IA

- CapyCoach como único agente inicial

### Próxima etapa

Fase 0 - Fundação do Monorepo

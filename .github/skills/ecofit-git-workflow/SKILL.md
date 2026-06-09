# EcoFit Git Workflow — Orientações para Agentes

**Versão:** 1.0.0  
**Último atualizado:** 2026-06-09  
**Aplicável:** Commits, pushes, branch management, worktrees, Git operations no projeto EcoFit

---

## 🎯 Visão Geral

Este documento estabelece o workflow correto de versionamento para o projeto EcoFit, incluindo estrutura de repositórios, branches, estratégia de commits e uso de worktrees. **Sempre consulte este guia ao realizar operações Git.**

---

## 📁 Estrutura de Repositórios

### Workspace (Monorepo) - devoJR

```
c:\Users\morai\Desktop\devoJR/
├── .git ❌ NÃO DEVE EXISTIR - removido propositalmente
├── freelas/
│   └── ecoFIT/
│       ├── ecoFit/                              ← REPOSITÓRIO REAL
│       │   ├── .git/ ✅ Repositório raiz
│       │   ├── .github/skills/
│       │   ├── CHANGELOG.md
│       │   ├── README.md
│       │   └── [código do projeto]
│       └── ecoFit.worktrees/                    ← Worktrees de desenvolvimento
│           └── agents-figma-projeto-criacao/   ← Branch: agents/figma-projeto-criacao
│               ├── .git ✅ Link simbólico para ecoFit/.git
│               └── [mesmo conteúdo de ecoFit]
└── [outros projetos]
```

### 🚨 Regra de Ouro

**NUNCA operate em `/devoJR` diretamente para Git operations.**  
**SEMPRE opera em `/freelas/ecoFIT/ecoFit/` (repositório real) ou seu worktree associado.**

---

## 🔀 Branches

| Branch | Propósito | Pushable | Notas |
|--------|-----------|---------|-------|
| `main` | Produção/release | ✅ Sim | Base principal. Merge após revisão. |
| `agents/figma-projeto-criacao` | Design/UI workflow | ✅ Sim | Branch de desenvolvimento para Figma/design. Alinhada com main em b964952. |

---

## 📍 Caminhos Corretos para Operações

### Operações no Repositório Principal

```bash
# Correto - Repositório real
cd c:\Users\morai\Desktop\devoJR\freelas\ecoFIT\ecoFit
git status
git add [files]
git commit -m "[mensagem]"
git push origin [branch]
```

### Operações no Worktree (agents/figma-projeto-criacao)

```bash
# Correto - Worktree da branch de desenvolvimento
cd c:\Users\morai\Desktop\devoJR\freelas\ecoFIT\ecoFit.worktrees\agents-figma-projeto-criacao
git status
git add [files]
git commit -m "[mensagem]"
git push origin agents/figma-projeto-criacao
```

### ❌ Operações INCORRETAS

```bash
# ❌ NUNCA - Não é um repositório Git
cd c:\Users\morai\Desktop\devoJR
git status

# ❌ NUNCA - Causará confusão
cd c:\Users\morai\Desktop\devoJR\freelas\ecoFIT
git status
```

---

## 📝 Guia de Commits

### 1. Preparar Alterações

```bash
# Navegar até o repositório correto
cd c:\Users\morai\Desktop\devoJR\freelas\ecoFIT\ecoFit

# Verificar status
git status

# Adicionar arquivos específicos (preferido) ou todos
git add [caminho/arquivo]
# ou
git add .
```

### 2. Fazer Commit

```bash
# Commit com mensagem clara
git commit -m "tipo: descrição breve"

# Exemplos de tipos:
# - feat: nova funcionalidade
# - docs: alteração de documentação
# - fix: correção de bug
# - style: mudanças de formatação
# - refactor: refatoração de código
```

### 3. Fazer Push

```bash
# Push para a branch atual
git push origin [branch]

# Exemplos:
git push origin main                              # Push para main
git push origin agents/figma-projeto-criacao     # Push para worktree
```

---

## 🌿 Fluxo de Trabalho por Tipo de Tarefa

### Tarefa 1: Design/Figma no agents/figma-projeto-criacao

```bash
# 1. Navegar ao worktree
cd c:\Users\morai\Desktop\devoJR\freelas\ecoFIT\ecoFit.worktrees\agents-figma-projeto-criacao

# 2. Fazer alterações (editar arquivos, adicionar assets, etc)
# ... editar arquivos ...

# 3. Adicionar e commitar
git add .github/skills/ecofit-design/
git commit -m "docs: atualizações de design no EcoFit"

# 4. Push para agents/figma-projeto-criacao
git push origin agents/figma-projeto-criacao
```

### Tarefa 2: Atualizações de Documentação no main

```bash
# 1. Navegar ao repositório principal
cd c:\Users\morai\Desktop\devoJR\freelas\ecoFIT\ecoFit

# 2. Certificar que está em main
git branch          # Deve mostrar * main
git pull origin main  # Sincronizar com remoto

# 3. Fazer alterações
# ... editar README.md, CHANGELOG.md, etc ...

# 4. Adicionar e commitar
git add README.md CHANGELOG.md
git commit -m "docs: atualizar documentação"

# 5. Push para main
git push origin main
```

### Tarefa 3: Sincronizar agents com main

Quando `agents/figma-projeto-criacao` fica desatualizada:

```bash
# 1. No worktree agents
cd c:\Users\morai\Desktop\devoJR\freelas\ecoFIT\ecoFit.worktrees\agents-figma-projeto-criacao

# 2. Trazer atualizações de main
git fetch origin main
git merge origin/main

# 3. Resolver conflitos se houver
# ... editar conflitos se necessário ...
# git add .
# git commit -m "merge: sincronizar com main"

# 4. Push para agents/figma-projeto-criacao
git push origin agents/figma-projeto-criacao
```

---

## 📦 Remote Configuration

```
Remote: origin
URL: https://github.com/DeoliveiraJR/ecoFit.git
Branches Tracked:
  - main → origin/main
  - agents/figma-projeto-criacao → origin/agents/figma-projeto-criacao
```

---

## ✅ Checklist Antes de Fazer Operações Git

- [ ] Estou no diretório correto? (`ecoFit` ou `ecoFit.worktrees/agents-figma-projeto-criacao`)
- [ ] Executei `git status` para confirmar estado?
- [ ] Meus arquivos estão adicionados corretamente?
- [ ] Minha mensagem de commit é clara e descritiva?
- [ ] Verifico que vou fazer push para a branch correta?
- [ ] Sincronizei com o remoto antes de fazer push? (`git pull origin [branch]`)

---

## 🚨 Erros Comuns e Soluções

### Erro: "fatal: not a git repository"

```bash
# ❌ Você está no diretório errado
cd c:\Users\morai\Desktop\devoJR\freelas\ecoFIT\ecoFit

# ✅ Agora tente novamente
git status
```

### Erro: "Permission denied (publickey)"

Configurar SSH corretamente no GitHub. Verificar SSH key:
```bash
ssh -T git@github.com
```

### Erro: "Conflicts merging branches"

Ao sincronizar:
```bash
# 1. Ver conflitos
git diff

# 2. Resolver manualmente ou com editor
git add [arquivo]

# 3. Completar merge
git commit -m "merge: resolver conflitos"
```

---

## 📚 Referência Rápida de Comandos

| Comando | Uso |
|---------|-----|
| `git status` | Ver arquivos modificados |
| `git add [arquivo]` | Adicionar arquivo ao staging |
| `git commit -m "[msg]"` | Criar commit |
| `git push origin [branch]` | Enviar commits ao GitHub |
| `git pull origin [branch]` | Trazer commits do GitHub |
| `git branch` | Listar branches locais |
| `git log --oneline` | Ver histórico de commits |
| `git fetch origin` | Atualizar referências remotas |
| `git merge origin/[branch]` | Mesclar branch remota |

---

## 🔗 Referências

- **Repositório remoto:** https://github.com/DeoliveiraJR/ecoFit
- **Commit head atual:** b964952
- **Skills relacionadas:** [ecofit-design](../ecofit-design/SKILL.md)
- **Workspace:** `/freelas/ecoFIT/ecoFit`
- **Documentação do projeto:** [README.md](../../README.md)

---

## 📝 Histórico de Versão

- **v1.0.0** (2026-06-09): Estabelecimento inicial do workflow após resolução de estrutura de monorepo. Remoção de Git root em devoJR, documentação de caminhos corretos para repositório interno e worktrees.

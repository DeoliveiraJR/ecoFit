# EcoFit Development Workflow — Guia de Commits, Branches e Git

**Versão:** 1.0.0  
**Scope:** Git operations, commits, branches, push/pull, workflow  
**Mantido por:** Equipe de Desenvolvimento

---

## 🎯 Filosofia

**Uma branch, múltiplos caminhos:**
- `main` é a única branch permanente
- Features temporárias em branches `feature/*` quando necessário
- Tudo commita em `main` por padrão
- Branches temporárias são deletadas após merge

---

## 📍 Local Correto para Operações

```bash
# ✅ SEMPRE use este caminho
cd /c/Users/morai/Desktop/devoJR/freelas/ecoFIT/ecoFit

# ❌ NUNCA use este (não é um repositório Git)
cd /c/Users/morai/Desktop/devoJR
```

---

## 📝 Fluxo Padrão: Commit → Push em Main

### 1. Verificar Status

```bash
cd /c/Users/morai/Desktop/devoJR/freelas/ecoFIT/ecoFit
git status
```

### 2. Adicionar Alterações

```bash
# Arquivo específico
git add src/components/Button.tsx

# Múltiplos arquivos
git add src/components/ .github/

# Todos os arquivos
git add .
```

### 3. Fazer Commit

```bash
git commit -m "tipo: descrição breve"
```

**Tipos de commit:**
- `feat:` Nova funcionalidade
- `fix:` Correção de bug
- `docs:` Alteração de documentação
- `style:` Mudanças de formatação (sem lógica)
- `refactor:` Refatoração de código
- `test:` Testes
- `chore:` Atualização de dependências, configs
- `design:` Alterações de UI/Figma

**Exemplos:**
```bash
git commit -m "feat: adicionar componente Button"
git commit -m "docs: atualizar README"
git commit -m "design: criar 11 telas do MVP em Figma"
git commit -m "fix: corrigir spacing em Home screen"
```

### 4. Fazer Push

```bash
git push origin main
```

---

## 🌿 Fluxo Avançado: Feature Branches

Use quando precisar trabalhar em feature isolada **sem afetar main**.

### Criar Feature Branch

```bash
git checkout -b feature/nova-funcionalidade
# Equivalente: git switch -c feature/nova-funcionalidade
```

### Trabalhar na Feature

```bash
# Fazer alterações
# ... editar arquivos ...

# Commits normais
git add .
git commit -m "feat: implementar x"
git commit -m "feat: adicionar y"

# Fazer push para a branch
git push origin feature/nova-funcionalidade
```

### Fazer Merge em Main

```bash
# Voltar para main
git checkout main

# Trazer atualizações
git pull origin main

# Mesclar feature
git merge feature/nova-funcionalidade

# Fazer push
git push origin main

# Deletar feature branch (localmente)
git branch -d feature/nova-funcionalidade

# Deletar feature branch (remoto)
git push origin --delete feature/nova-funcionalidade
```

---

## 🔄 Sincronizar com Remoto

### Antes de começar trabalho novo

```bash
git pull origin main
```

### Depois de fazer push, verificar remoto

```bash
git fetch origin
git log origin/main -3
```

---

## ⚠️ Cenários Especiais

### Desfazer último commit (não fez push)

```bash
# Manter alterações
git reset --soft HEAD~1

# Descartar alterações
git reset --hard HEAD~1
```

### Corrigir mensagem do último commit

```bash
git commit --amend -m "mensagem corrigida"
```

### Se fez push com erro, usar revert

```bash
# Criar commit de revert (seguro para remoto)
git revert HEAD
git push origin main
```

### Mudar de branch antes de commitar

```bash
# Salvar alterações temporariamente
git stash

# Trocar de branch
git checkout main

# Voltar para a branch anterior
git checkout feature/algo
git stash pop
```

---

## 📊 Checklist Antes de Push

- [ ] Executei `git status` e revisei alterações?
- [ ] Testei localmente? (npm run dev, build, etc)
- [ ] Executei `git pull origin main` para sincronizar?
- [ ] Minha mensagem de commit é clara?
- [ ] Não estou comitando arquivos sensíveis? (`.env`, `node_modules`)
- [ ] `.gitignore` está atualizado?

---

## 📚 Comandos Rápidos

| Comando | O que faz |
|---------|----------|
| `git status` | Mostra status atual |
| `git add [arquivo]` | Adiciona arquivo ao staging |
| `git commit -m "[msg]"` | Cria commit |
| `git push origin main` | Envia para GitHub main |
| `git pull origin main` | Traz atualizações do GitHub |
| `git branch` | Lista branches locais |
| `git branch -a` | Lista todas as branches (local + remoto) |
| `git log --oneline` | Histórico resumido de commits |
| `git log -p` | Histórico com mudanças detalhadas |
| `git diff` | Mostra diferenças não commitadas |
| `git stash` | Salva alterações temporariamente |
| `git stash pop` | Recupera alterações salvas |

---

## 🔗 Remote Configuration

```
Remote: origin
URL: https://github.com/DeoliveiraJR/ecoFit.git
Branch tracking: main → origin/main
```

---

## ❌ Erros Comuns

### "fatal: not a git repository"

```bash
# ❌ Você não está no repositório
# ✅ Navegar para o lugar certo
cd /c/Users/morai/Desktop/devoJR/freelas/ecoFIT/ecoFit
git status
```

### "Your branch is behind origin/main"

```bash
# Trazer atualizações
git pull origin main
```

### "Permission denied (publickey)"

Configure SSH:
```bash
ssh -T git@github.com
# Se falhar, adicionar chave: ssh-add ~/.ssh/id_rsa
```

### "merge conflict"

```bash
# 1. Ver conflitos
git diff

# 2. Editar arquivos conflitados (abrir em editor)
# 3. Adicionar
git add [arquivo]

# 4. Completar merge
git commit -m "merge: resolver conflitos"
```

---

## 🚀 Quando usar esta skill

- Fazer commit de código
- Fazer push para GitHub
- Criar/deletar branches
- Sincronizar com remoto
- Resolver conflitos
- Desfazer commits
- Onboarding de desenvolvedores

---

## 🏗️ Entender a Arquitetura

> Para entender a estrutura de diretórios do projeto, fluxo de dados e como componentes se relacionam:
> 
> ### 🔗 [ARCHITECTURE.md](../../ARCHITECTURE.md) ← **Estrutura de Diretórios**
> ### 🔗 [ARCHITECTURE_MAINTENANCE.md](../../ARCHITECTURE_MAINTENANCE.md) ← **Como Manter Atualizado**

Consulte estes arquivos antes de:
- Criar novos diretórios ou módulos
- Refatorar estrutura de pastas
- Entender onde adicionar novos componentes/serviços
- Atualizar a arquitetura após mudanças estruturais

---

## 📖 Referências

- [Git Official Docs](https://git-scm.com/doc)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Flow](https://guides.github.com/introduction/flow/)
- **[ARCHITECTURE.md](../../ARCHITECTURE.md)** ← Estrutura de diretórios e diagrama de fluxo
- **[ARCHITECTURE_MAINTENANCE.md](../../ARCHITECTURE_MAINTENANCE.md)** ← Como manter arquitetura atualizada

**Repository:** https://github.com/DeoliveiraJR/ecoFit  
**Local:** `/freelas/ecoFIT/ecoFit`

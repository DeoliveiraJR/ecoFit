# 🔄 Código Compartilhado

Utilitários, tipos, constantes e código reutilizável entre mobile e backend.

## Conteúdo

- **types/** - Tipos TypeScript compartilhados (User, Workout, Habit, etc)
- **constants/** - Constantes (URLs, timeouts, mensagens)
- **utils/** - Funções utilitárias (formatação, validação, etc)
- **hooks/** - React hooks compartilhados (se aplicável)

## Exemplo de Estrutura

```
shared/
├── types/
│   ├── user.ts
│   ├── workout.ts
│   ├── habit.ts
│   └── chat.ts
├── constants/
│   ├── api.ts
│   └── messages.ts
└── utils/
    ├── formatting.ts
    ├── validation.ts
    └── date.ts
```

## Usando

Importe desde qualquer lugar do projeto:

```typescript
import { User, Workout } from 'shared/types'
import { API_BASE_URL } from 'shared/constants'
```

# 📱 Mobile App — React Native + Expo

## Visão Geral

Aplicativo mobile do EcoFit para iOS e Android.

## Estrutura

- **app/** - Roteamento Expo Router
  - **(auth)/** - Telas de autenticação (login, onboarding)
  - **(app)/** - Telas principais (home, chat, treinos, etc)
- **components/** - Componentes reutilizáveis (Button, Card, Input, etc)
- **screens/** - Componentes de página/tela
- **hooks/** - Custom React hooks
- **services/** - Integração com API, chamadas HTTP
- **stores/** - State management (Zustand/Context)
- **styles/** - Estilos globais, temas
- **types/** - TypeScript types e interfaces

## Tecnologias

- React Native
- Expo
- Expo Router
- NativeWind (Tailwind)
- TypeScript

## Rodando

```bash
npm install
npm run dev
```

## Estrutura de Roteamento

```
app/
├── index.tsx          → Splash
├── (auth)
│   ├── login.tsx
│   ├── onboarding.tsx
│   └── register.tsx
└── (app)
    ├── home.tsx
    ├── chat.tsx
    ├── workouts.tsx
    ├── habits.tsx
    ├── massage.tsx
    └── profile.tsx
```

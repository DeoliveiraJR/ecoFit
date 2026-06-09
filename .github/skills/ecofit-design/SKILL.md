# EcoFit Design System — Guia Visual e de Componentes

**Versão:** 1.0.0  
**Scope:** Design, UI/UX, Figma, componentes, cores, tipografia  
**Mantido por:** Equipe de Design

---

## 🎨 Paleta de Cores

| Nome | Hex | RGB | Uso |
|------|-----|-----|-----|
| **Teal** | `#00EBD0` | 0, 235, 208 | CTA, headers, destaque principal |
| **Pink** | `#D96AB4` | 217, 106, 180 | Destaque secundário, badges |
| **Navy** | `#0F172A` | 15, 23, 42 | Background escuro, texto principal |
| **Card** | `#1E293B` | 30, 41, 59 | Fundo de cards |
| **Border** | `#334155` | 51, 65, 85 | Linhas divisórias |
| **Gray** | `#64748B` | 100, 116, 139 | Texto secundário |
| **White** | `#FFFFFF` | 255, 255, 255 | Texto claro, backgrounds claros |
| **Blue** | `#06B6D4` | 6, 182, 212 | Informações, links |
| **Purple** | `#735CC6` | 115, 92, 198 | Achievements, destaque terciário |

---

## 🔤 Tipografia

### Fontes

- **Headings (H1, H2, H3):** Poppins Bold, 400-700 weight
- **Body text:** Inter Regular, 400 weight
- **Small text:** Inter, 300-400 weight

### Tamanhos

- **H1:** 32px / 400px devices
- **H2:** 24px
- **H3:** 18px
- **Body:** 16px
- **Small:** 14px

---

## 📱 Componentes Principais

### Button

```
Dimensões: 48px height, 100% width (mobile)
Cores: Background Teal, text White
Radius: 8px
State: pressed (opacity 0.8), disabled (opacity 0.5)
```

### Card

```
Background: Card color (#1E293B)
Radius: 12px
Padding: 16px
Border: 1px solid Border color
Shadow: subtle (0 2px 8px rgba(0,0,0,0.1))
```

### Input Field

```
Background: Navy com opacity 0.5
Border: 1px Border color
Radius: 8px
Padding: 12px 16px
Placeholder: Gray
Focus: Border Teal
```

### Navigation

```
Position: Bottom
Height: 56px
Icons: 5 main screens (Home, Chat, Treinos, Hábitos, Mais)
Active: Teal background, White icon
Inactive: Gray icon
```

---

## 🦫 Mascote CapyCoach

**Descrição:** Capivara atleta nerd com óculos, energética e motivadora

**Uso:**
- Splash screen: full body, 200x240px
- Home screen: small avatar, 48x48px (circulado)
- Chat bubbles: medium, 80x100px
- Onboarding: medium, 100x120px

**Estilo:** Cartoon, cores primárias da paleta, expressões amigáveis

---

## 📐 Layout & Spacing

- **Device width:** 390px (mobile)
- **Safe area:** 16px margins
- **Grid:** 4-column grid para cards
- **Gap:** 12px entre elementos
- **Padding:** 16px padrão, 12px reduzido, 24px expandido

---

## 🎥 Figma Reference

**File ID:** V2QRBuCzkJCFKEYYBs76nJ  
**Status:** 11 screens prototype (Splash, Onboarding, Login, Home, Chat, Treinos, Exercício, Hábitos, Massoterapia, Perfil, Mais)

**Access:** [EcoFit MVP — Editável](https://figma.com/design/V2QRBuCzkJCFKEYYBs76nJ)

---

## 📋 11 Screens Overview

1. **Splash** - Logo, mascot, progress indicator
2. **Onboarding** - Welcome flow, CTA "Vamos começar"
3. **Login** - Auth form, OAuth options
4. **Home** - Dashboard, metrics, agenda
5. **Chat CapyCoach** - Conversational AI interface
6. **Treinos** - Workout list, start button
7. **Exercício** - Video + sets table
8. **Hábitos** - Habit cards with progress
9. **Massoterapia** - Calendar + booking
10. **Perfil** - User settings, menu
11. **Mais** - Additional options menu

---

## 🎨 Design Tokens (CSS Variables)

```css
--color-teal: #00EBD0;
--color-pink: #D96AB4;
--color-navy: #0F172A;
--color-card: #1E293B;
--color-border: #334155;
--color-gray: #64748B;
--color-white: #FFFFFF;
--color-blue: #06B6D4;
--color-purple: #735CC6;

--font-heading: 'Poppins', sans-serif;
--font-body: 'Inter', sans-serif;

--radius-small: 4px;
--radius-medium: 8px;
--radius-large: 12px;

--spacing-xs: 4px;
--spacing-sm: 8px;
--spacing-md: 12px;
--spacing-lg: 16px;
--spacing-xl: 24px;
```

---

## 🚀 Quando usar esta skill

- Criação de componentes novos no Figma
- Decisões de cor e tipografia
- Prototipagem de telas
- Revisar consistency visual
- Onboarding de novos designers

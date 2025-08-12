# Meu Portfólio | Lucas Farias

Portfólio pessoal desenvolvido com React + TypeScript + Vite + Tailwind CSS.

## 📂 Estrutura de Componentes Recomendada

```
src/
├── components/         # Componentes reutilizáveis
│   ├── ui/              # Componentes básicos (Button, Card, etc.)
│   ├── layout/          # Componentes de layout (Header, Footer, etc.)
│   └── common/          # Componentes comuns (Loading, Modal, etc.)
├── sections/            # Seções específicas do portfólio
│   ├── Hero/
│   ├── About/
│   ├── Projects/
│   ├── Skills/
│   └── Contact/
├── pages/               # Páginas (se usar roteamento)
├── hooks/               # Custom hooks
├── utils/               # Funções utilitárias
├── types/               # Tipos TypeScript
└── assets/              # Imagens, ícones, etc.
```

### 🎯 Organização por Categoria:

**1. `components/ui/`** - Componentes básicos reutilizáveis:
- `Button.tsx`, `Card.tsx`, `Badge.tsx`, `Input.tsx`

**2. `components/layout/`** - Estrutura da página:
- `Header.tsx`, `Footer.tsx`, `Navigation.tsx`, `Sidebar.tsx`

**3. `sections/`** - Seções específicas do portfólio:
- Cada pasta com `index.tsx` e estilos próprios
- Ex: `Hero/Hero.tsx`, `Projects/ProjectCard.tsx`

**4. `components/common/`** - Componentes compartilhados:
- `Loading.tsx`, `ErrorBoundary.tsx`, `SEO.tsx`

### 💡 Convenções:
- **PascalCase** para nomes de componentes
- **Arquivo index.tsx** em cada pasta para facilitar imports
- **Co-localização** de estilos e testes junto ao componente
- **Barrel exports** para imports limpos

---

## ⚡ Tecnologias

Este projeto utiliza React + TypeScript + Vite com HMR e algumas regras do ESLint.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      ...tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      ...tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      ...tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

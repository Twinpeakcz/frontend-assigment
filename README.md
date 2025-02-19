# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

- Replace `tseslint.configs.recommended` to `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
- Optionally add `...tseslint.configs.stylisticTypeChecked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from 'eslint-plugin-react'

export default tseslint.config({
  // Set the react version
  settings: { react: { version: '18.3' } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```


# Zadání 

## 1) Načtení dat
Načtěte data z API CoinGecko:

**Endpoint:**  
[`https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd`](https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd)

**Požadovaná data:**
- `id` (Coin ID)
- `symbol` (Symbol)
- `current_price` (Current Price)
- `market_cap` (Market Cap)
- `total_volume` (Total Volume)
- `last_updated` (Last Updated)
- `price_change_percentage_24h` (24h Change %)

---

## 2) Tabulka (React + Tailwind)
Vytvoř **responzivní tabulku** v **Reactu** s **Tailwind CSS**, která zobrazí výše uvedené údaje.

---

## 3) Stylování tabulky
**Design by měl připomínat návrh** .  
**Čas a datum** formátuj do čitelného formátu (např. `25 May 2023, 12:00`).  
**Sloupec `24h Change (%)`**:
- Pokud je hodnota **kladná** ➝ 🟢 **Zelená barva** 
- Pokud je hodnota **záporná** ➝ 🔴 **Červená barva**
- "Load more" tlačítko zobrazí nové okno, kde bude kompletní tabulka všech dostupných kryptoměn. 

---

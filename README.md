<<<<<<< HEAD
 



# Expense Tracker with Dashboard  

## Overview  
This is a **Vue 3** expense tracker application that allows users to **add, remove, and track expenses** while visualizing data through a **dashboard with charts**. The project balances **functionality** and **data visualization**, making it useful for users who want insights into their spending patterns.  

## Features  
- **Add and Remove Expenses**: Users can dynamically input expenses.  
- **Expense List**: Displays all added expenses with options to remove them.  
- **Interactive Charts**: A visual breakdown of expenses using `vue-chartjs`.  
- **Modern UI**: Clean, purple-themed layout with an intuitive interface.  

## Technologies Used  
- **Vue 3** (Composition API)  
- **Vue Chart.js** for data visualization  
- **Tailwind CSS** for styling  

## Setup Instructions  
1. Clone the repository:  
   ```sh
   git clone <repository-url>
   cd expense-tracker
   ```  
2. Install dependencies:  
   ```sh
   npm install
   ```  
3. Run the development server:  
   ```sh
   npm run dev
   ```  
4. Open the app in your browser at `http://localhost:5173` (or as specified).  

## Future Enhancements  
- Category-based expense tracking  
- Monthly budget limits  
- Exporting reports  

---

Clone and have fun! 🚀
=======
# expense-tracker

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Run End-to-End Tests with [Playwright](https://playwright.dev)

```sh
# Install browsers for the first run
npx playwright install

# When testing on CI, must build the project first
npm run build

# Runs the end-to-end tests
npm run test:e2e
# Runs the tests only on Chromium
npm run test:e2e -- --project=chromium
# Runs the tests of a specific file
npm run test:e2e -- tests/example.spec.ts
# Runs the tests in debug mode
npm run test:e2e -- --debug
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
>>>>>>> e360f55 (Changed app.vue,expenselist.vue,expensechart.vue to show the graph and add and remove expenses)

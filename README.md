# ⚙️ ESLint & Prettier Jejolare.dev Shareable Config (React/Next.js/Node.js)

Step-by-step guide of importing the config into the project.

---

## 📦 Step 1: Install Config As A Dev Dependency

Install required package:

```bash
npm i -D eslint-config-jejolare
```

---

## 🛠️ Step 2: Configuration Files

### `.eslintrc.js`

This ESLint configuration extends the Jejolare.dev config. You can override any rules as needed.

```js
module.exports = {
  // Or 'jejolare/backend' for Node.js app
  extends: ['jejolare/frontend'],

  // This is needed only if you use TypeScript
  settings: {
    'import/resolver': {
      typescript: {
        project: './tsconfig.json',
      },
    },
  },
};

```

---

### `.eslintignore`

Use any ESLint ignore config you need. Here's a template you can use.

```
submodules/
node_modules/

dist/
build/
.next/

*.log
*.tmp
.temp/
migrations/

public/
static/

.vscode/
.idea/

.env*
```

---

### `prettier.config.mjs`

This Prettier configuration extends the Jejolare.dev config. You can override any rules as needed as well.

```js
/** @type {import("prettier").Config} */
import prettierConfig from 'eslint-config-jejolare/prettier';

export default prettierConfig;
```

---

### `.prettierignore`

Use any Prettier ignore config you need. Here's a template you can use.

```
node_modules
build
dist
coverage
.next
.env
*.lock
submodules/
migrations/
```

---

### Useful Scripts in `package.json`

```json
"scripts": {
  "format": "prettier --write .",
  "format:check": "prettier --check .",
  "eslint": "eslint . --ext .js,.ts,.tsx,.jsx --fix"
}
```

---

## ✅ Done!

The Jejolare.dev ESLint & Prettier plugin has been successfully imported.
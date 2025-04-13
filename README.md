# 🧼 Conventional Commits Setup (Husky + Commitlint)

This repo shows how to set up **Conventional Commits** in your project using `Husky` and `Commitlint` 🚀.

---

## 📦 1. Install Dev Dependencies

```bash
npm install --save-dev husky @commitlint/{config-conventional,cli}
```

## 🛠 2. Set up Commitlint
Create a file in the root of your project named `commitlint.config.js`:
```js
module.exports = {
  extends: ['@commitlint/config-conventional'],
};
```

## ⚙️ 3. Enable Husky Git Hooks
Run this command to set up Husky:
```bash
npx husky
```
Then update your `package.json`:
```json
"scripts": {
  "prepare": "husky install"
}
```

## 🧱 4. Add Commit-msg Hook
Create the commit-msg hook manually by running this script:
```bash
echo "npx --no -- commitlint --edit \$1" > .husky/commit-msg
```

## 🧪 5. Test It
Try committing with a bad message:
```bash
git commit -m "stuff"
```
❌ This will be rejected.

Try a good one:
```bash
git commit -m "chore: configure husky for conventional commits enforcement"
```
✅ You're good to go!

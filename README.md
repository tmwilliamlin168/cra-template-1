# Steps to reproduce template

`npx create-react-app --template typescript`

Add `"baseUrl": "src"` to `"compilerOptions"` in `tsconfig.json`

Add to `"eslintConfig"` in `package.json`:

```json
"rules": {
  "eqeqeq": "error"
}
```

In folder `.vscode`, create `settings.json`:

```json
{
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```

And `extensions.json`:

```json
{
  "recommendations": ["dbaeumer.vscode-eslint"]
}
```

`npm i @typescript-eslint/eslint-plugin`, add `"plugin:@typescript-eslint/recommended"` to `"eslintConfig"."extends"` in `package.json`

`npm i prettier eslint-config-prettier`, add `"prettier"` to `"eslintConfig"."extends"` in `package.json`

Add to `settings.json`:

```json
"editor.formatOnSave": true,
"editor.defaultFormatter": "esbenp.prettier-vscode"
```

Add `"esbenp.prettier-vscode"` to `extensions.json`

Create `.prettierrc.json`:

```json
{
  "singleQuote": true
}
```

`npm i husky lint-staged`, `npx husky install`, `npx husky add .husky/pre-commit "npx lint-staged"`

Create `lint-staged.config.js`:

```js
module.exports = {
  '**/*.(ts|tsx)': () => 'npx tsc --noEmit',
  '**/*.(ts|tsx|js)': (filenames) => [
    `npx eslint --fix ${filenames.join(' ')}`,
    `npx prettier --write ${filenames.join(' ')}`,
  ],
  '**/*.(md|json)': (filenames) =>
    `npx prettier --write ${filenames.join(' ')}`,
};
```

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

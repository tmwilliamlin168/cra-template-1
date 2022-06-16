# Steps to reproduce template

`npx create-react-app --template typescript`

Add `"baseUrl": "src"` to `"compilerOptions"` in `tsconfig.json`

Add to `"eslintConfig"` in `package.json`:

```json
"rules": {
  "eqeqeq": "error"
}
```
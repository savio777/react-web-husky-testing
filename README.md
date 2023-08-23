### links:

- [lint](https://medium.com/how-to-react/config-eslint-and-prettier-in-visual-studio-code-for-react-js-development-97bb2236b31a)
- [husky](https://medium.com/how-to-react/how-to-use-husky-and-lint-staged-in-react-js-to-push-your-error-free-code-to-git-f9a382d4b624)
- [testes com vitest](https://eternaldev.com/blog/testing-a-react-application-with-vitest)
- [commitlint](https://thiagolopessilva.medium.com/um-pequeno-guia-para-verificar-o-padr%C3%A3o-de-commits-no-git-usando-huksy-7-x-parte-1-e5183bc15cd7)

### tips:

- comando criação do projeto: `yarn create vite vite-react-husky-test --template react-ts` (criação padrão do react vem agora com next)
- instalar dependências: `yarn` | `npm install`
- rodar `git init`
- instalação **husky** e **_**lint-staged**_** `npm --dev husky lint-staged`
- adicionar script `"postinstall": "husky install"`
- rodar comando para adicionar o pré commit do husky com **_**lint-staged**_**: `npx husky add .husky/pre-commit "npx lint-staged"`
- instalar **_**vitest**_**: `yarn add -D vitest`
- rodar comando para adicionar o pré push com comando para testes com **_**vitest**_**: `npx husky add .husky/pre-push "yarn test"`
- instalar **commitlint**: `yarn add -D @commitlint/cli @commitlint/config-conventional`
- adicionar **commitlint** aos git hooks do husky `npx husky add .husky/commit-msg 'npx --no -- commitlint --edit "$1"'`

### todo:

- [x] criar projeto
- [x] iniciar git
- [x] instalra huskt e lint-staged
- [x] adicionar scripts
- [x] adicionar pre commit e push
- [x] configração test
- [x] adicionar padrões mensagens commit

##### config lint-staged:

- `.lintstagedrc`

````json
  {"**/*.{ts,tsx}": ["eslint --fix"]}```
````

##### config test:

- instalar `vitest`
- adicionar script: `"test": "vitest --run"`
- `vite.config.ts`

```ts
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],

  test: {
    globals: true,
    environment: "jsdom",
  },
});
```

##### config commitlint:
- `commitlint.config.cjs`
```js
module.exports = {
  extends: ["@commitlint/config-conventional"],
  rules: {
    "type-enum": [
      2,
      "always",
      [
        "improv",
        "build",
        "chore",
        "ci",
        "docs",
        "feat",
        "fix",
        "perf",
        "refactor",
        "revert",
        "style",
        "test",
      ],
    ],
  },
};
```

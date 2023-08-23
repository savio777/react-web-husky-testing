### links:

- [lint](https://medium.com/how-to-react/config-eslint-and-prettier-in-visual-studio-code-for-react-js-development-97bb2236b31a)
- [husky](https://medium.com/how-to-react/how-to-use-husky-and-lint-staged-in-react-js-to-push-your-error-free-code-to-git-f9a382d4b624)
- [testes com vitest](https://eternaldev.com/blog/testing-a-react-application-with-vitest)

### tips:

- comando criação do projeto: `yarn create vite vite-react-husky-test --template react-ts` (criação padrão do react vem agora com next)
- instalar dependências: `yarn` | `npm install`
- rodar `git init`
- instalação husky e lint-staged `npm --dev husky lint-staged`
- adicionar script `"postinstall": "husky install"`
- rodar comando para adicionar o pré commit do husky com lint-staged: `npx husky add .husky/pre-commit "npx lint-staged"`
- rodar comando para adicionar o pré push com comando para testes: `npx husky add .husky/pre-push "yarn test"`


### todo:
- [x] criar projeto
- [x] iniciar git
- [x] instalra huskt e lint-staged
- [x] adicionar scripts
- [x] adicionar pre commit e push
- [x] configração test
- [ ] adicionar padrões mensagens commit

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

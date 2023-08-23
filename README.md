### links:

- [lint](https://medium.com/how-to-react/config-eslint-and-prettier-in-visual-studio-code-for-react-js-development-97bb2236b31a)
- [husky](https://medium.com/how-to-react/how-to-use-husky-and-lint-staged-in-react-js-to-push-your-error-free-code-to-git-f9a382d4b624)

### tips:

- comando criação do projeto: `yarn create vite vite-react-husky-test --template react-ts` (criação padrão do react vem agora com next)
- instalar dependências: `yarn` | `npm install`
- rodar `git init`
- instalação husky e lint-staged `npm --dev husky lint-staged`
- adicionar script `"postinstall": "husky install"`
- adicionar arquivo `.lintstagedrc`, inserir `{"**/*.{ts,tsx}": ["eslint --fix"]}`
- rodar comando para adicionar o pré commit do husky com lint-staged `npx husky add .husky/pre-commit "npx lint-staged"`


#### todo:
- rodar teste no pre-push

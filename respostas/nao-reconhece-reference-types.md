Eventualmente, o Cypress não reconhece o comando que adiciona o Intellisense ao projeto:

```js
  /// <reference types="cypress" />
```
Ao passar o mouse sobre o trecho, é exibido o erro:
- *Cannot find type definition file for 'cypress'*

**Possíveis soluções:**
1. Desinstalar e instalar novamente: `npm uninstall cypress` & `npm install -D cypress`
2. No VSCode, digitar ctrl + shift + p, e selecionar 'Typescript: Restart TS Server'


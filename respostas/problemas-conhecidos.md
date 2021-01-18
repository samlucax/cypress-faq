## Resolução de problemas comuns
--------------------------------------------------------------------------
### Problema
* Porque meu npm run report:clean não apaga a pasta mochawesome-report nem full_report.json?
### Resolução
Esse é um problema bem comum. Uma sugestão é usar uma biblioteca que:
1. identifica o sistema operacional
2. executa o comando para excluir diretórios de acordo com o SO

Uma dessas bibliotecas é o rimraf. Basicamente, para usar siga os seguintes passos:
1. instale o rimraf no projeto: npm install -D rimraf
2. substitua os comandos rm -rf por rimraf

Assim você evita por exemplo de, seus testes funcionarem localmente mas falharem quando subir em uma integração contínua (que pode executar em máquinas Windows, Linux, MacOS, etc.)

--------------------------------------------------------------------------
### Problema
- Só consigo exibir quais testes passaram no azure com o xunit ou consigo com o mochawesomereport?
### Resolução
- A exibição, sim. Uma das coisas que podem ser feitas é publicar o relatório do mochawesome como artefato do build, assim ele fica disponível para download

--------------------------------------------------------------------------
### Problema
- Incluir delay para o preenchimento de um campo
### Resolução
cy.get('.align-items-end > .form-control').type('1500', { delay: 200})
cy.get('campo').type('texto do campo', { delay: tempo})

--------------------------------------------------------------------------
### Problema
- Trabalhando com dois ambientes - configurar package.json
### Resolução
- URL  produção
"cypress:run:develop": "cypress run --config baseUrl=",
- URL develop
    "cypress:run:master": "cypress run --config baseUrl="
    
--------------------------------------------------------------------------    
### Problema
- Como gerar relatório de cobertura de teste com Cypress

### Resolução
- Podemos usar o @cypress/code-coverage   
- Temos uma aula expecificamente sobre isso no módulo 4. #06 "Cobertura de código usando os testes de UI"

--------------------------------------------------------------------------    
### Problema
Selecionar um determinado valor de uma lista com valor mínimo e valor máximo

### Resolução
cy.get('campo select').select(chance.integer({ min: 1, max: 15 }));

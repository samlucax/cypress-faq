Tradução da documentação: https://docs.cypress.io/faq/questions/general-questions-faq

# Perguntas gerais

- O Cypress é gratuito e de código aberto?
- Quais sistemas operacionais o Cypress possui suporte?
- Vocês oferecem suporte a aplicativos mobile nativos?
- Como o Cypress é diferente da ferramenta de teste 'X'?

## O Cypress é gratuito e de código aberto?

O [Test Runner](https://docs.cypress.io/guides/core-concepts/test-runner "Test Runner") é gratuito para download e de código aberto (licença MIT). Seu uso é gratuito. Nosso serviço de [Dashboard](https://docs.cypress.io/guides/dashboard/introduction "Dashboard") é uma aplicação web que oferece diferentes planos de cobrança (incluindo um plano gratuito) para quando você deseja registrar suas execuções de teste no CI.

Por favor, consulte nossa [página de preços](https://www.cypress.io/pricing "página de preços") para mais detalhes.

## Quais sistemas operacionais o Cypress possui suporte?

Você pode[ instalar o Cypress](https://docs.cypress.io/guides/getting-started/installing-cypress " instalar o Cypress") no Mac, Linux e Windows. Para obter informações adicionais, consulte nossos [requisitos de sistema](https://docs.cypress.io/guides/getting-started/installing-cypress#System-requirements "requisitos de sistema").

## Vocês oferecem suporte a aplicativos mobile nativos?

O Cypress nunca poderá ser executado em um aplicativo mobile nativo, mas podemos testar algumas funcionalidades de navegadores da web mobile e testar aplicativos mobile que são desenvolvidos em um navegador, como com a estrutura [Ionic](https://ionicframework.com/ "Ionic") ou [React Expo](https://glebbahmutov.com/blog/testing-react-native-app-using-cypress/ "React Expo").

Atualmente você pode controlar o tamanho da janela de visualização (viewport) com o comando cy.viewport() para testar a aparência responsiva em um site ou aplicativo da web. Você também pode imitar certos comportamentos, como deslizar usando [comandos personalizados](https://docs.cypress.io/api/cypress-api/custom-commands "comandos personalizados").

Você pode ler sobre o [teste de aplicativos móveis com Ionic e Cypress](https://www.cypress.io/blog/2020/07/08/end-to-end-testing-mobile-apps-with-ionic-and-cypress/ "teste de aplicativos móveis com Ionic e Cypress") e ver como gerenciamos o teste de diferentes visualizações responsivas em uma [aplicação](https://github.com/cypress-io/cypress-realworld-app "aplicação").

## Como o Cypress é diferente da ferramenta de teste 'X'?

O Cypress Test Runner é um aplicativo / estrutura / serviço híbrido, tudo em um. Leva um pouco de outras ferramentas de teste, junta tudo e melhora. Como por exemplo:



### Mocha

Mocha é uma estrutura de teste para JavaScript (link aqui  Mocha). O [Mocha](http://mochajs.org/ "Mocha") fornece os métodos `it`, `describe`, `beforeEach`. O Cypress não é diferente do Mocha, ele realmente usa o Mocha por baixo dos panos. Todos os seus testes serão escritos em cima da interface `bdd` do Mocha.

### Karma

[Karma](http://karma-runner.github.io/ "Karma") é um executor de teste de unidade para JavaScript, funciona com [Jasmine](https://jasmine.github.io/ "Jasmine"), [Mocha](http://mochajs.org/ "Mocha") ou qualquer outra estrutura de teste de JavaScript.

Karma também observa seus arquivos JavaScript, recarrega automaticamente quando eles são alterados e também é sinaliza sobre a falha / aprovação de seus testes. Ele é executado a partir da linha de comando.

O Cypress essencialmente substitui o Karma porque já faz tudo isso e muito mais.

### Capybara

A ferramenta específica do Ruby que permite escrever testes de integração para sua aplicação web é o [Capybara](http://teamcapybara.github.io/capybara/ "Capybara"). No mundo Rails, esta é a ferramenta ideal para testar seu aplicativo. Ele usa o [Sauce Labs](https://saucelabs.com/ "Sauce Labs") (ou outro driver headless) para interagir com os navegadores. Sua API consiste em comandos que consultam os elementos DOM, executam ações do usuário, navegam, etc.

O Cypress essencialmente substitui a Capybara porque faz todas essas coisas e muito mais. A diferença é que em vez de testar seu aplicativo em um console sem interface gráfica do usuário, você verá seu aplicativo o tempo todo. Você nunca teria que fazer uma captura de tela para depurar porque todos os comandos fornecem instantaneamente o estado de sua aplicação enquanto são executados. Se qualquer comando falhar, você terá um erro legível explicando por que ele falhou. Não há "adivinhações" durante o debugging.

Frequentemente, o Capybara começa a não funcionar tão bem em aplicativos JavaScript complexos. Além disso, tentar aplicar TDD em sua aplicação é difícil. Você precisa escrever primeiro o código do aplicativo (e normalmente, atualizar manualmente o navegador após as alterações) até que ele funcione. A partir daí você escreve testes, mas perde todo o valor do TDD.


### Protractor

O uso do [Protractor](http://www.protractortest.org/ "Protractor") fornece uma ótima interface baseada em Promises no Selenium, o que torna menos complicado lidar com código assíncrono. O Protractor vem com todos os recursos do Capybara e, essencialmente, sofre dos mesmos problemas.

O Cypress substitui o Protractor porque faz todas essas coisas e muito mais. Uma diferença importante é que o Cypress permite que você escreva seus testes de unidade e testes de integração na mesma ferramenta, em vez de dividir este trabalho entre Karma e Protractor.

Além disso, o Protractor está muito focado no AngularJS, enquanto o Cypress foi projetado para funcionar com qualquer estrutura JavaScript. Protractor, por ser baseado em Selenium, ainda é muito lento e é proibitivo ao tentar aplicar TDD em seu aplicativo. O Cypress, por outro lado, é executado na velocidade que seu navegador e aplicativo são capazes de executar e renderizar; não há excessos adicionais.

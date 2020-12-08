Quando executar o comando `npx cypress open`, e ocorrer um erro semelhante a esse: Failed to deserialize the v8 snapshot blob.

![failed serialize v8 snapshot](https://github.com/adsguilherme/cypress-faq/blob/main/src/assets/failedtodeserializethev8snapshotblob.png)

Executar o seguinte comando `npx cypress install --force`.

Depois que concluir o processo executar `npx cypress open`.

**E agora o processo irá ocorrer com sucesso!**

Maiores detalhes em: https://github.com/cypress-io/cypress/issues/5440

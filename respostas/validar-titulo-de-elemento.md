Uma validação muito comum em nosso dia a dia é conferir o título ou outros atributos de um determinado elemento.

Vejo o exemplo de html abaixo:

```html
<button id="exemplo" title="Texto incrível"></button>
```

Nesse caso, o *id* e o *title* são atributos do elemento `button`.

Agora que já sabemos o que são atributos de um elemento, vejamos como validar os valores destes atributos ⚡️

Nesse caso a sintaxe é a seguinte:

```js
cy.get(elemento)
    .should('have.attr', 'atributo que voce quer', 'valor que voce quer')

```

Levando para o seu exemplo, ficaria assim:

```js
cy.get('button[type="submit"]')
      .should('have.attr', 'title', 'Texto incrível')
```

Complementando o exemplo acima, dentro do should são 3 argumentos:

1. `have.attr`, responsável por obter o valor de um determinado atributo
2. `title` é o atributo que queremos buscar *neste exemplo*.
3. `Texto incrível` é o valor que esperamos que o atributo tenha *neste exemplo*.

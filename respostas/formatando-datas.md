// Método para formatar uma data, pois há alguns inputs do tipo date os quais trabalham em formato americano.
// Dessa forma, nosso amigo Samuel Lucas ajudou a criar um método o qual insere entradas do tipo: 'DD-MM-YYYY', nos inputs os quais recebem o formato: 'YYY-MM-DD'
// Estranho, né? Mas essa solução foi encaixada com êxito para o problema, pois a partir da bibiloteca 'chance.date', foi possível formatar os dados.

// Antes de tudo, certifique-se de estar usando a biclioteca chance, caso não tenha, é só usar o comando:
// npm i chance
// No seu aquivo, você vai precisar do:

// let Chance = require('chance')
// let chance = new Chance()

// Método criado
configurarData() {
    let splittedDate = chance.date({ string: true, american: false }).split('/')

    if (splittedDate[0] < 10) {
      splittedDate[0] = `0${splittedDate[0]}`
    }

    if (splittedDate[1] < 10) {
      splittedDate[1] = `0${splittedDate[1]}`
    }

    let formattedDate = `${splittedDate[2]}-${splittedDate[1]}-${splittedDate[0]}`
    
    // Pronto!
    // Com a data formatada na variável 'formattedDate', é só encontrar no elemento o qual existe no DOM do html referente ao campo 'data' e inserir, pois já atende ao padrão brasileiro, que é 'DD-MM-YYYY'
    
    cy.get(el.inputStartDate).type(formattedDate);
    cy.get(el.inputEndDate).type(formattedDate);

  }

  Data randômica que foi gerada:
  ![data que foi formatada inserida no respectivo campo](https://github.com/szabo01/cypress-faq/blob/main/src/assets/data-ramdomica-formatada.png)
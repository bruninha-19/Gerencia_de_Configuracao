# Testes Automatizados com Cypress

## Teste de Busca

Este arquivo contém testes automatizados para validar a funcionalidade de busca de livros no sistema.

### **Descrição**
- Os testes são escritos utilizando a biblioteca Cypress.
- Validam a busca por títulos existentes e verificam o comportamento do sistema ao pesquisar termos inexistentes.

---

### **Código**

```javascript
describe('Teste de Busca', () => {
  it('Buscar livro por título', () => {
    cy.visit('/'); // Página inicial

    // Seleciona o campo de busca pelo atributo name e insere o título do livro
    cy.get('input[name="termo"]').type('Harry Potter e a Pedra Filosofal');

    // Seleciona o botão de busca mais próximo do campo usando `.closest()` ou especificando o contexto do formulário
    cy.get('form[action="/pesquisar"] button[type="submit"]').click();

    // Verifica se o redirecionamento ocorreu corretamente
    cy.url().should('include', '/pesquisar?termo=Harry+Potter+e+a+Pedra+Filosofal');

    // Verifica se os resultados aparecem
    cy.contains('Resultados para "Harry Potter e a Pedra Filosofal"').should('be.visible');
  });

  it('Buscar termo inexistente', () => {
    cy.visit('/'); // Página inicial

    // Seleciona o campo de busca pelo atributo name e insere um termo inexistente
    cy.get('input[name="termo"]').type('Livro Inexistente');

    // Seleciona o botão de busca mais próximo do campo
    cy.get('form[action="/pesquisar"] button[type="submit"]').click();

    // Verifica se o redirecionamento ocorreu corretamente
    cy.url().should('include', '/pesquisar?termo=Livro+Inexistente');

    // Verifica se a mensagem de nenhum resultado aparece
    cy.contains('Nenhum livro encontrado para "Livro Inexistente"').should('be.visible');
  });
});


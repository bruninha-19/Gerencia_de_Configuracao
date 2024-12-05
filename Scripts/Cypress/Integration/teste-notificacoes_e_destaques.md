# Testes Automatizados com Cypress

## Teste de Notificações e Destaques

Este arquivo contém testes automatizados para validar as funcionalidades relacionadas a notificações e destaques de livros no sistema.

### **Descrição**
- Os testes são escritos utilizando a biblioteca Cypress.
- Validam cenários como marcar e desmarcar livros como destaques e verificar se os destaques aparecem na tela principal.

---

### **Código**

```javascript
describe('Teste de Notificações e Destaques', () => {
  // Realiza login antes de cada teste
  beforeEach(() => {
    // Realiza o login antes de cada teste
    cy.visit('/login');
    cy.get('#email').type('wellythonsouza105@gmail.com'); // Preencha com as credenciais válidas
    cy.get('#password').type('novaSenha123');
    cy.contains('Entrar').click(); // Substitua 'Entrar' pelo texto visível no botão
    cy.url().should('include', '/usuario');
    cy.contains('Meu Perfil').should('be.visible'); // Verifica se o login foi bem-sucedido
  });

  it('Deve marcar um livro como destaque', () => {
    cy.visit('/usuario');
    // Localiza e clica no primeiro botão de "Marcar Destaque"
    cy.get('form[action^="/marcar-destaque/"] button#marcar').first().click();
    // Verifica se o livro foi marcado como destaque
    cy.get('form[action^="/desmarcar-destaque/"] button#desmarcar').should('exist');
  });

  it('Deve desmarcar um livro como destaque', () => {
    cy.visit('/usuario');
    // Localiza e clica no primeiro botão de "Desmarcar Destaque"
    cy.get('form[action^="/desmarcar-destaque/"] button#desmarcar').first().click();
    // Verifica se o livro foi removido dos destaques
    cy.get('form[action^="/marcar-destaque/"] button#marcar').should('exist');
  });

  it('Verifica se os livros em destaque aparecem na tela principal', () => {
    cy.visit('/');
    // Verifica se a seção de destaques contém pelo menos um livro
    cy.get('.container-destaques .livro').should('have.length.greaterThan', 0);
  });
});


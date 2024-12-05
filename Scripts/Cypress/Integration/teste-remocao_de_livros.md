# Testes Automatizados com Cypress

## Teste de Remoção de Livros

Este arquivo contém testes automatizados para validar a funcionalidade de remoção de livros no sistema.

### **Descrição**
- Os testes são escritos utilizando a biblioteca Cypress.
- Validam cenários como remoção bem-sucedida de livros, verificação de exclusão e tratamento de erros ao tentar remover livros que não pertencem ao usuário.

---

### **Código**

```javascript
describe('Teste de Remoção de Livros', () => {
  // Realiza login antes de cada teste
  beforeEach(() => {
    cy.visit('/login');
    cy.get('#email').type('wellythonsouza105@gmail.com'); // Credenciais válidas
    cy.get('#password').type('novaSenha123');
    cy.contains('Entrar').click();
    cy.url().should('include', '/usuario');
    cy.contains('Meu Perfil').should('be.visible'); // Verifica login bem-sucedido
  });

  it('Deve remover um livro existente', () => {
    cy.visit('/usuario'); // Navega para a página do usuário
    cy.get('.livro-container .remover').first().click({ force: true }); // Clica no botão "Remover" do primeiro livro
    cy.contains('Livro removido com sucesso').should('be.visible'); // Verifica a mensagem de sucesso
  });

  it('Verifica se o livro removido não aparece mais na lista de "Meus Livros"', () => {
    cy.visit('/usuario');
    cy.contains('Título do Livro Removido').should('not.exist'); // Verifica que o livro não está mais na lista
  });

  it('Deve exibir erro ao tentar remover livro que não pertence ao usuário', () => {
    // Simulação de um acesso indevido ao botão de remoção de outro livro
    cy.request({
      method: 'POST',
      url: '/remover-livro/999', // ID de um livro que não pertence ao usuário
      failOnStatusCode: false, // Garante que o teste continua mesmo com erro esperado
    }).then((response) => {
      expect(response.status).to.eq(403); // Verifica se a resposta é "403 Forbidden"
    });
  });
});


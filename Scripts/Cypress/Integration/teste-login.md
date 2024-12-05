# Testes Automatizados com Cypress

## Teste de Adição de Livros

Este arquivo contém testes automatizados para validar o fluxo de login e a funcionalidade de adição de livros ao sistema.

### **Descrição**
- Os testes são escritos utilizando a biblioteca Cypress.
- Antes de cada teste, é realizado o login no sistema com credenciais válidas.
- Os testes verificam tanto o cenário positivo (campos preenchidos corretamente) quanto cenários negativos (campos obrigatórios não preenchidos).

---

### **Código**

```javascript
describe('Teste de Login e Adição de Livros', () => {
  beforeEach(() => {
      // Realiza o login antes de cada teste
      cy.visit('/login');
      cy.get('#email').type('wellth@gmail.com'); // Preencha com as credenciais válidas
      cy.get('#password').type('110706');
      cy.contains('Entrar').click(); // Substitua 'Entrar' pelo texto visível no botão
      cy.url().should('include', '/usuario');
      cy.contains('Meu Perfil').should('be.visible'); // Verifica se o login foi bem-sucedido
  });

  it('Adicionar livro com todos os campos preenchidos corretamente', () => {
      cy.visit('/adicionar-livro');
      cy.get('#titulo').type('Livro Sem Descrição', { force: true });
      cy.get('#autor').type('Autor Teste');
      cy.get('#editora').type('Editora Teste');
      cy.get('#ano').type('2024');
      cy.get('#isbn').type('123456789');
      cy.get('#descricao').type('Descrição de teste do livro.');
      cy.get('#paginas').type('200');
      cy.get('#estado').type('Novo');
      cy.get('#preco').type('50.00');
      cy.get('#categoria').select('ficcao');
      cy.get('#imagem').attachFile('livro.png'); // Certifique-se de que o arquivo existe no diretório "fixtures"
      cy.get('#button-add').click({ force: true });
  });

  it('Verificar campos obrigatórios sem preencher', () => {
    cy.visit('/adicionar-livro');
  
    // Tenta submeter o formulário
    cy.get('#button-add').click();
  
    // Verifica se os campos obrigatórios estão marcados como inválidos
    cy.get('#titulo:invalid').should('exist'); // O campo "titulo" é inválido
    cy.get('#autor:invalid').should('exist'); // O campo "autor" é inválido
    cy.get('#editora:invalid').should('exist'); // O campo "editora" é inválido
    cy.get('#ano:invalid').should('exist'); // O campo "ano" é inválido
    cy.get('#isbn:invalid').should('exist'); // O campo "isbn" é inválido
    cy.get('#descricao:invalid').should('exist'); // O campo "descricao" é inválido
    cy.get('#paginas:invalid').should('exist'); // O campo "paginas" é inválido
    cy.get('#estado:invalid').should('exist'); // O campo "estado" é inválido
    cy.get('#preco:invalid').should('exist'); // O campo "preco" é inválido
    cy.get('#categoria:invalid').should('exist'); // O campo "categoria" é inválido
    cy.get('#imagem:invalid').should('exist'); // O campo "imagem" é inválido
  });
});


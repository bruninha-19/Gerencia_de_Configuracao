# Testes Automatizados com Cypress

## Teste de Edição de Livros

Este arquivo contém testes automatizados para validar a funcionalidade de edição de livros no sistema.

### **Descrição**
- Os testes são escritos utilizando a biblioteca Cypress.
- Validam cenários de edição bem-sucedida de livros e o tratamento de erros ao tentar editar livros que não pertencem ao usuário.

---

### **Código**

```javascript
describe('Teste de Edição de Livros', () => {
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

  it('Editar livro "O Senhor dos Anéis" com sucesso', () => {
    cy.visit('/editar-livro/15'); // ID do livro "O Senhor dos Anéis"
    cy.get('#titulo').clear().type('O Senhor dos Anéis - Edição Atualizada');
    cy.get('#autor').clear().type('Alex Tolkien');
    cy.get('#editora').clear().type('UFAM Press');
    cy.get('#ano').clear().type('2024'); // Novo ano
    cy.get('#isbn').clear().type('9876543210987'); // Novo ISBN
    cy.get('#descricao')
      .clear()
      .type('Uma edição revisada e ampliada da obra clássica de fantasia.');
    cy.get('#paginas').clear().type('1200'); // Novo número de páginas
    cy.get('#estado').clear().type('Usado - Excelente');
    cy.get('#preco').clear().type('89.90'); // Novo preço
    cy.get('#categoria').select('fantasia'); // Atualizar categoria
    cy.get('button[type="submit"]').click({ force: true }); // Botão para salvar alterações
    cy.contains('Alterações salvas com sucesso').should('be.visible');
  });

  it('Editar livro que não pertence ao usuário', () => {
    cy.visit('/editar-livro/2'); // Supondo que o ID 2 seja de outro usuário
    cy.contains('Você não tem permissão para editar este livro').should('be.visible');
  });
});


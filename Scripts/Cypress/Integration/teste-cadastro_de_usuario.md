# Testes Automatizados com Cypress

## Teste de Cadastro de Usuário

Este arquivo contém testes automatizados para validar a funcionalidade de cadastro de usuários no sistema.

### **Descrição**
- Os testes são escritos utilizando a biblioteca Cypress.
- Validam o fluxo de cadastro de novos usuários, incluindo cenários positivos e negativos.

---

### **Código**

```javascript
describe('Teste de Cadastro de Usuário', () => {
  it('Deve cadastrar usuário com todos os campos preenchidos corretamente', () => {
    cy.visit('/cadastro');
    cy.get('#nome').type('João');
    cy.get('#sobrenome').type('Silva');
    cy.get('#email').type('joao2.silva@teste.com');
    cy.get('#telefone').type('999999999');
    cy.get('#whatsapp').type('999999999');
    cy.get('#password').type('senha123');
    cy.get('#confirma_password').type('senha123');
    cy.get('#button-cadastro').click({ force: true });
    
    // Verifica se o redirecionamento ocorreu corretamente
    cy.url().should('include', '/sucesso'); 
    
    // Verifica se a mensagem de sucesso está visível
    cy.contains('Usuário cadastrado com sucesso!').should('be.visible');
  });

  it('Deve exibir erro ao tentar cadastrar com senhas diferentes', () => {
    cy.visit('/cadastro');
    cy.get('#password').type('senha123');
    cy.get('#confirma_password').type('senhaErrada');
    cy.get('#button-cadastro').click({ force: true });
    
    // Verifica a exibição da mensagem de erro
    cy.contains('As senhas não coincidem').should('be.visible');
  });

  it('Deve exibir erro ao tentar cadastrar com email já existente', () => {
    cy.visit('/cadastro');
    cy.get('#email').type('wellythonsouza105@gmail.com');
    cy.get('#button-cadastro').click({ force: true });
    
    // Verifica a exibição da mensagem de erro
    cy.contains('Email já cadastrado').should('be.visible');
  });
});


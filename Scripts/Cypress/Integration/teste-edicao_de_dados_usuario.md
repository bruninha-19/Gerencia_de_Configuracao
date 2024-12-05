# Testes Automatizados com Cypress

## Teste de Edição de Dados do Usuário

Este arquivo contém testes automatizados para validar a funcionalidade de edição de dados do usuário no sistema.

### **Descrição**
- Os testes são escritos utilizando a biblioteca Cypress.
- Validam o fluxo de edição de informações pessoais, alteração de senha e tratamento de erros, como senhas não coincidentes.

---

### **Código**

```javascript
describe('Teste de Edição de Dados do Usuário', () => {
    // Realiza login antes de cada teste
    beforeEach(() => {
        cy.visit('/login');
        cy.get('#email').type('usuario@teste.com'); // Preencha com as credenciais válidas
        cy.get('#password').type('senhaAtual123');
        cy.contains('Entrar').click();
        cy.url().should('include', '/usuario'); // Verifica se o login foi bem-sucedido
    });

    it('Deve atualizar os dados do usuário corretamente', () => {
        cy.visit('/editar-usuario');
        cy.get('#nome').clear().type('João Atualizado');
        cy.get('#sobrenome').clear().type('Silva Atualizado');
        cy.get('#email').clear().type('joao.silva@atualizado.com');
        cy.get('#telefone').clear().type('999999999');
        cy.get('#whatsapp').clear().type('888888888');
        cy.get('#button-salvar').click({ force: true });

        // Verifica se a mensagem de sucesso é exibida
        cy.contains('Dados atualizados com sucesso!').should('be.visible');
    });

    it('Deve alterar a senha corretamente', () => {
        cy.visit('/editar-usuario');
        cy.get('#senha-atual').type('senhaAtual123');
        cy.get('#nova-senha').type('novaSenha123');
        cy.get('#confirma-nova-senha').type('novaSenha123');
        cy.get('#button-salvar').click({ force: true });

        // Verifica se a mensagem de sucesso é exibida
        cy.contains('Senha alterada com sucesso!').should('be.visible');
    });

    it('Deve exibir erro ao tentar alterar a senha com valores não coincidentes', () => {
        cy.visit('/editar-usuario');
        cy.get('#senha-atual').type('senhaAtual123');
        cy.get('#nova-senha').type('novaSenha123');
        cy.get('#confirma-nova-senha').type('outraSenha123');
        cy.get('#button-salvar').click({ force: true });

        // Verifica se a mensagem de erro é exibida
        cy.contains('As senhas não coincidem').should('be.visible');
    });
});


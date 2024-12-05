# Testes Automatizados com Cypress

## Teste de Fluxo de Compra com Negociação

Este arquivo contém testes automatizados para validar o fluxo de compra e negociação de livros no sistema.

### **Descrição**
- Os testes são escritos utilizando a biblioteca Cypress.
- Validam cenários como redirecionamento para a página de negociação, integração com o WhatsApp e tratamento de erros para livros inexistentes.

---

### **Código**

```javascript
describe('Teste de Fluxo de Compra com Negociação', () => {
    // Realiza login antes de cada teste
    beforeEach(() => {
        cy.visit('/login');
        cy.get('#email').type('wellythonsouza105@gmail.com'); // Preencha com as credenciais válidas
        cy.get('#password').type('novaSenha123');
        cy.contains('Entrar').click();
        cy.url().should('include', '/usuario'); // Verifica se o login foi bem-sucedido
    });

    it('Deve redirecionar para a área de negociação ao clicar em "Comprar"', () => {
        cy.visit('/');
        cy.get('.conteiner-livros .content a').first().click(); // Clica no botão "Comprar" do primeiro livro
        cy.url().should('include', '/livro/'); // Verifica se foi redirecionado para a página do livro
        cy.contains('Negociar').should('be.visible'); // Verifica se o botão "Negociar" está visível
    });

    it('Deve redirecionar para o WhatsApp ao clicar no botão de negociação', () => {
        // Acessa a página onde o botão de negociação está presente
        cy.visit('/livro/15', { failOnStatusCode: false }); // Permite continuar mesmo se houver um erro 404
    
        // Clica no botão "Negociar"
        cy.get('a.button[href="/negociar"]').click();
    
        // Verifica se o redirecionamento foi para o WhatsApp
        cy.url().should('include', 'https://wa.me/');
    });

    it('Deve exibir erro ao tentar negociar um livro inexistente', () => {
        cy.visit('/livro/999', { failOnStatusCode: false }); // Visita um ID inexistente
        cy.contains('Livro não encontrado').should('be.visible'); // Verifica a mensagem de erro
    });
});


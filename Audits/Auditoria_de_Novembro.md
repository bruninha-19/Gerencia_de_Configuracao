# Relatório de Auditoria - Planejamento de Testes do Sistema

**Data da Auditoria:** 28/11/2024  
**Equipe Participante:**
- **Carlos Uchôa** (Gerente de Projeto)
- **Bruna Miranda** (Desenvolvedora Frontend)
- **Wellython Sá** (Desenvolvedor Backend)
- **Julia Farias** (Analista de Banco de Dados)

---

## **Objetivo da Auditoria**
Definir e organizar os testes a serem realizados no sistema para validar as principais funcionalidades, garantindo que estejam alinhadas com os requisitos do projeto.

---

## **Funcionalidades e Cenários de Teste Definidos**

### **1. Teste de Login**
- **Descrição:** Verifica a funcionalidade de login do usuário.
- **Cenários:**
  - Login com credenciais válidas.
  - Login com senha incorreta (exibe mensagem de erro).
  - Login com usuário inexistente (exibe mensagem de erro).

---

### **2. Teste de Cadastro de Usuário**
- **Descrição:** Valida o fluxo de cadastro de novos usuários.
- **Cenários:**
  - Cadastro com todos os campos preenchidos corretamente.
  - Cadastro com senhas diferentes (exibe mensagem de erro).
  - Cadastro com e-mail já existente (exibe mensagem de erro).

---

### **3. Teste de Adição de Livros**
- **Descrição:** Verifica a funcionalidade de adicionar novos livros ao sistema.
- **Cenários:**
  - Adicionar livro com todos os campos preenchidos corretamente.
  - Adicionar livro sem preencher campos obrigatórios (exibe mensagem de erro).
  - Verificar se o livro aparece na tela de "Meus Livros".

---

### **4. Teste de Edição de Livros**
- **Descrição:** Verifica se os livros podem ser editados corretamente.
- **Cenários:**
  - Editar os detalhes de um livro já existente (ex.: título, descrição).
  - Alterar a imagem de um livro.
  - Tentar editar um livro que não pertence ao usuário (exibe mensagem de erro).

---

### **5. Teste de Remoção de Livros**
- **Descrição:** Valida a funcionalidade de exclusão de livros.
- **Cenários:**
  - Remover um livro existente.
  - Verificar se o livro não aparece mais na lista de "Meus Livros".
  - Tentar remover um livro que não pertence ao usuário (exibe mensagem de erro).

---

### **6. Teste de Notificações e Destaques**
- **Descrição:** Avalia as funcionalidades relacionadas a notificações e destaques.
- **Cenários:**
  - Marcar um livro como destaque.
  - Desmarcar um livro como destaque.
  - Verificar se os livros em destaque aparecem na tela principal.

---

### **7. Teste de Listagem e Filtro de Livros**
- **Descrição:** Valida a exibição de livros e a organização por categorias.
- **Cenários:**
  - Acessar a tela de listagem de livros e verificar se os livros aparecem corretamente.
  - Filtrar livros por categoria (ex.: Romance, Ficção).
  - Verificar se os livros relacionados aparecem na página de detalhes de um livro.

---

### **8. Teste de Edição de Dados do Usuário**
- **Descrição:** Verifica a funcionalidade de edição de informações pessoais do usuário.
- **Cenários:**
  - Atualizar nome, sobrenome, e-mail, telefone e WhatsApp.
  - Alterar a senha do usuário.
  - Tentar alterar com senhas diferentes (exibe mensagem de erro).

---

### **9. Teste de Busca de Livros**
- **Descrição:** Verifica a funcionalidade de busca de livros no sistema.
- **Cenários:**
  - Buscar livro por título.
  - Buscar livro por autor.
  - Buscar livro por categoria.
  - Buscar termo inexistente (exibe mensagem "Nenhum resultado encontrado").

---

## **Próximos Passos**
- **Execução dos Testes:** Os testes definidos serão executados para validar o funcionamento das funcionalidades.
- **Relatório Pós-Teste:** Após a execução, será realizada uma nova auditoria para analisar os resultados e identificar possíveis problemas ou melhorias.
- **Cronograma:** A execução dos testes está prevista para ser concluída até 01/12/2024.

---

## **Conclusão**
A auditoria inicial de definição de testes foi concluída com sucesso. As funcionalidades prioritárias foram identificadas, e cenários de teste detalhados foram definidos para validação futura.

---

### **Responsáveis pela Aprovação**
- **Carlos Uchôa** (Gerente de Projeto)  
- **Bruna Miranda** (Desenvolvedora Frontend)  
- **Wellython Sá** (Desenvolvedor Backend)  
- **Julia Farias** (Analista de Banco de Dados)  

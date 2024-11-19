# Arquitetura de Software

A arquitetura **MVC (Model-View-Controller)** é um padrão de design utilizado no desenvolvimento de software para separar a lógica da aplicação em três componentes interconectados. Essa separação facilita a manutenção, a escalabilidade e a organização do código.

---

## Representação da Arquitetura MVC

Para representar a arquitetura **MVC (Model-View-Controller)**, utilizamos um diagrama que ilustra a interação entre os três componentes principais:

![Arquitetura MVC](https://drive.google.com/uc?id=1RIEKyGHjCyCJRxCcyo3ZC9wpHBKeFQXr)

---

### Ciclo de Interação na Arquitetura MVC

1. **Usuário Interage com a View**:
   - O usuário realiza alguma ação na interface gráfica, como clicar em um botão ou preencher um formulário.

2. **View Chama o Controller**:
   - A View captura a interação do usuário e envia uma solicitação ao Controller.

3. **Controller Processa a Solicitação**:
   - O Controller recebe a solicitação, processa a lógica de negócios associada e interage com o Model para obter ou modificar dados.

4. **Model Atualiza os Dados**:
   - O Model realiza operações no banco de dados, como buscar, inserir, atualizar ou deletar dados, e pode notificar a View sobre qualquer mudança nos dados.

5. **View Atualiza a Interface**:
   - A View é atualizada com os novos dados fornecidos pelo Model e apresenta esses dados ao usuário.

6. **Usuário Vê os Dados Atualizados**:
   - O usuário vê a interface atualizada e pode realizar novas interações, reiniciando o ciclo.

---

Este ciclo de interação garante uma separação clara entre a interface do usuário (**View**), a lógica de negócios (**Controller**) e os dados (**Model**), facilitando a manutenção, a escalabilidade e a organização da aplicação.

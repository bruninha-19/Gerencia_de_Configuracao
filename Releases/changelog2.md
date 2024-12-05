# Changelog

## [released]
### Added
- Testes automatizados com Cypress cobrindo funcionalidades-chave do sistema.
- Feedback inicial sobre falhas e aprovações dos testes.

---

## [1.2] - 2024-11-28
### Testes Implementados

#### **Testes Aprovados**
- **Login do Usuário:**
  - Login com credenciais válidas e inválidas.
  - Validação de mensagens de erro apropriadas para casos de falha.

- **Cadastro de Usuário:**
  - Cadastro com todos os campos preenchidos corretamente.
  - Mensagens de erro apropriadas para senhas diferentes e e-mails já existentes.

- **Busca de Livros:**
  - Busca por títulos existentes e inexistentes.
  - Mensagens claras para resultados encontrados ou não encontrados.

- **Notificações e Destaques:**
  - Funcionalidade de marcar e desmarcar livros como destaque.
  - Validação da exibição de livros em destaque na tela principal.

#### **Testes com Problemas Identificados**
- **Adição de Livros:**
  - Falha ao validar campos obrigatórios vazios.
  - Livros adicionados não foram exibidos corretamente em "Meus Livros".

- **Edição de Livros:**
  - Erro ao salvar alterações para livros pertencentes ao usuário.
  - Permissão inadequada para edição de livros de outros usuários.

- **Remoção de Livros:**
  - Livro removido ainda aparece na lista de "Meus Livros".
  - Mensagem de erro ausente ao tentar remover livro de outro usuário.

- **Listagem e Filtros:**
  - Filtros por categorias não funcionaram corretamente.
  - Livros relacionados ausentes na página de detalhes.

- **Fluxo de Compra com Negociação:**
  - Redirecionamento para WhatsApp falhou em algumas tentativas.
  - Botão "Negociar" ausente para alguns livros.

- **Edição de Dados do Usuário:**
  - Alteração de senha não foi salva corretamente.
  - Mensagens de erro para senhas não coincidentes ausentes.

---

### Known Issues
- Correção necessária nos formulários para garantir validações de campos obrigatórios.
- Melhorar permissões e mensagens de erro para funcionalidades relacionadas a livros de outros usuários.
- Ajustar os filtros de categorias e exibição de livros relacionados na página de detalhes.
- Revisar integração com o WhatsApp para garantir redirecionamento correto em "Negociação".

---

## Próximas Etapas
- Corrigir os problemas conhecidos com base nos testes realizados.
- Realizar nova rodada de testes após correções.
- Atualizar o changelog com os resultados da próxima versão.

---

## [1.2.0] - 2024-11-15
### Added
- Tela de categorias de livros com filtro por gênero.
- Funcionalidade de marcar e desmarcar livros como destaques.

---

## [1.1.0] - 2024-11-01
### Added
- Cadastro, login e adição básica de livros.
- Funcionalidades iniciais de troca e venda de livros.

---

## Notas
Este changelog é baseado nos resultados dos testes realizados em 2024-11-28.

# Relatório de Auditoria - Identificação e Resolução de Problemas no Sistema

**Data da Auditoria:** 18/10/2024  

## Equipe Participante:
- **Carlos Uchôa** (Gerente de Projeto)
- **Bruna Miranda** (Desenvolvedora Frontend)
- **Julia Farias** (Desenvolvedora Backend)
- **Wellython Sá** (Analista de Banco de Dados)

---

## Objetivo da Auditoria
Avaliar problemas relatados no sistema, classificar sua gravidade, discutir soluções, e definir um plano de ação para correções e melhorias, garantindo a funcionalidade e estabilidade do sistema.

---

## Pautas da Auditoria
1. Revisão das **issues** abertas no sistema.
2. Classificação dos problemas por gravidade e impacto.
3. Discussão de soluções técnicas com a equipe.
4. Planejamento e atribuição de responsabilidades para a resolução dos problemas.
5. Avaliação de melhorias para prevenir futuros erros.

---

## Problemas Identificados

### Tabela Resumida

| **ID** | **Descrição do Problema**                                           | **Categoria**      | **Responsável**  | **Impacto**    | **Prazo**     |
|--------|----------------------------------------------------------------------|--------------------|------------------|----------------|---------------|
| #9     | Falha ao processar pagamentos no sistema                            | Fato Incorreto     | Julia Farias     | Crítico        | 20/11/2024    |
| #8     | Notificações não estão sendo enviadas para transações               | Omissão            | Bruna Miranda    | Alto           | 22/11/2024    |
| #7     | Falha ao adicionar livros para troca ou venda                      | Fato Incorreto     | Julia Farias     | Alto           | 20/11/2024    |
| #6     | Os usuários não fornecem visualização do histórico de trocas        | Omissão            | Wellython Sá     | Médio          | 24/11/2024    |
| #5     | Falha ao editar informações de perfil de outros usuários            | Fato Incorreto     | Julia Farias     | Médio          | 23/11/2024    |
| #4     | Relatórios de transações não estão sendo gerados                    | Fato Incorreto     | Wellython Sá     | Crítico        | 21/11/2024    |
| #3     | Erro ao gerenciar usuários no sistema                               | Omissão            | Bruna Miranda    | Alto           | 24/11/2024    |
| #2     | Erro na moderação de conteúdo pelo administrador                    | Fato Incorreto     | Wellython Sá     | Crítico        | 20/11/2024    |

---

## Discussão e Análise dos Problemas

### 1. Problemas Críticos

#### **Erro ao processar pagamentos (#9):**
- **Impacto:** Afeta diretamente o fluxo financeiro do sistema, impedindo a conclusão de transações.
- **Causa Provável:** Falha na integração com a API de pagamento.
- **Solução:** Revisar a lógica de validação e conexão com a API. Julia será responsável.

#### **Relatórios de transações não gerados (#4):**
- **Impacto:** Compromete o controle financeiro e a transparência dos administradores.
- **Causa Provável:** Queries SQL mal otimizadas no banco de dados.
- **Solução:** Reestruturar as consultas SQL para otimizar a geração de relatórios. Wellython será responsável.

#### **Erro na moderação de conteúdo pelo administrador (#2):**
- **Impacto:** Impede a remoção de conteúdo inapropriado, afetando a confiabilidade da plataforma.
- **Causa Provável:** Falha no gerenciamento de permissões no backend.
- **Solução:** Revisar os middleware de autenticação e autorização. Wellython será responsável.

---

### 2. Melhorias Propostas

#### **Notificações para transações (#8):**
- **Impacto:** Reduz a eficiência da comunicação com os usuários.
- **Solução:** Bruna será responsável por implementar um sistema de notificações push.

#### **Histórico de trocas ausente (#6):**
- **Impacto:** Prejudica a experiência do usuário e dificulta o rastreamento de atividades.
- **Solução:** Wellython deve criar uma tabela adicional no banco para armazenar o histórico de trocas.

#### **Erro ao gerenciar usuários (#3):**
- **Impacto:** Dificulta o gerenciamento administrativo de contas.
- **Solução:** Bruna deve revisar o frontend e corrigir as interações com o backend.

---

## Plano de Ação

### 1. Correções Prioritárias
- **Problemas Críticos:** Resolver até 21/11/2024.
- **Responsáveis:**
  - Julia: Pagamentos (#9), perfis de usuários (#5).
  - Wellython: Relatórios (#4), moderação (#2).

### 2. Implementação de Melhorias
- **Melhorias Funcionais:** Resolver até 24/11/2024.
- **Responsáveis:**
  - Bruna: Notificações (#8), gerenciamento de usuários (#3).
  - Wellython: Histórico de trocas (#6).

### 3. Revisão e Testes
- **Responsável:** Carlos Uchôa.
- **Ação:** Realizar testes de validação para garantir a funcionalidade de cada correção.

---

## Resultados Esperados
- Melhorias na experiência do usuário com a adição de notificações e histórico de trocas.
- Correção de problemas críticos, especialmente relacionados a pagamentos e relatórios financeiros.
- Estabilidade e confiabilidade do sistema para administradores e usuários.

---

## Responsáveis
- **Coordenação Geral:** Carlos Uchôa
- **Desenvolvimento Frontend:** Bruna Miranda
- **Desenvolvimento Backend:** Julia Farias
- **Banco de Dados:** Wellython Sá

---

## Aprovação do Relatório:
**Carlos Uchôa**  
Gerente do Projeto

---

## Detalhes Adicionais
Este relatório detalha cada problema identificado, responsável por resolvê-lo, e prazos para conclusão. Ele pode ser complementado com um acompanhamento contínuo via ferramentas como **Trello**, **Jira** ou outros gerenciadores de projetos.


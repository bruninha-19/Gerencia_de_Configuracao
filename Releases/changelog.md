# Changelog - Versão 1.1

**Data de Liberação:** 28/10/2024  

## Funcionalidades Adicionadas
- **Funcionalidade "Esqueci Minha Senha" na Área de Login:**
  - Agora os usuários podem redefinir suas senhas por meio de um link enviado para o e-mail cadastrado.
  - Implementação de uma API para geração e validação de tokens de redefinição de senha.
  - Integração com o serviço de envio de e-mails (Nodemailer).
  - Adicionado botão "Esqueci Minha Senha" na interface de login.
  - Tela adicional para inserção de e-mail e redefinição de senha.

## Justificativa
- A funcionalidade foi implementada para resolver a falta de um mecanismo de recuperação de senha, que gerava insatisfação entre os usuários e aumento no volume de solicitações ao suporte técnico.

## Impactos
- **Positivo:**
  - Experiência do usuário aprimorada.
  - Redução no número de solicitações de suporte técnico relacionadas à recuperação de senha.
- **Negativo:**
  - Pequeno aumento no consumo de recursos do servidor devido ao envio de e-mails.

## Melhorias Técnicas
- Criação de uma tabela no banco de dados para armazenar tokens temporários de redefinição de senha, garantindo segurança no processo.
- Reforço na validação e expiração de tokens para evitar uso indevido.

## Próximos Passos
- Monitorar o desempenho do sistema após a implementação, especialmente o volume de envios de e-mails.
- Considerar a implementação de recuperação por perguntas de segurança ou autenticação multifator como etapas futuras.

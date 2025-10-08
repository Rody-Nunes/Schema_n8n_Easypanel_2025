# Este repositório contém um workflow/schema para Easypanel.
exportado do n8n, com todas as dependências, necessárias, em modo Fila e MCP ativo.

## Como isntalar:
Copie o Schema que deixamos, abra no seu Programa de edição como cursor, Visual Studio code etc...

Edite o codigo mudando suas credênciais, do postgres e do Redis, caso não tenha essas dependências instaladas no seu Easypanel, instalar antes.
Campos a preencher:

Nome_do_servico_Redis_AQUI: nome serviço Redis criado no Easypanel

Porta_do_Redis_AQUI: porta Redis (geralmente 6379)

Senha_Redis_AQUI: senha Redis definida no Easypanel

Nome_do_servico_Postgres_AQUI: nome serviço Postgres criado no Easypanel

Porta_do_Postgres_AQUI: porta Postgres (geralmente 5432)

Nome_do_Banco_AQUI: nome do banco de dados criado

Usuario_Postgres_AQUI: usuário do banco Postgres

Senha_Postgres_AQUI: senha do usuário Postgres

SUA_CHAVE_ENCRYPTION_AQUI: chave de criptografia n8n (pode gerar com comando ou usar senha segura)

## Depois que preeencher com suas credeciais, Siga o tutorial abaixo.
Clique em Personalizado: 
<img width="1006" height="544" alt="image" src="https://github.com/user-attachments/assets/9593fb8e-916f-4270-8b49-ec98a12049b0" />

## Criar apartir de esquema:
<img width="997" height="469" alt="image" src="https://github.com/user-attachments/assets/5026d740-3e98-45d9-990c-784936e32fe3" />

Cola seu schema editado, e clique em criar, é só esperar o n8n subir as dependências e tudo estará funcional.
<img width="547" height="486" alt="image" src="https://github.com/user-attachments/assets/392e2376-c77d-4d1a-ae5b-60b44ec6353f" />


## Caso o seu dê erro revise suas credênciais se preencheu corretamente e tente novamente.

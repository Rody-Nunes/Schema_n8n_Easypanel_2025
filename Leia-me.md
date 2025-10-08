# Este repositório contém um workflow/schema para Easypanel.
exportado do n8n, com todas as dependências, necessárias, em modo Fila e MCP ativo.

# Como isntalar: 
Copie o Schema que deixamos, abra no seu Programa de edição como cursor, Visual Studio code etc...

- Edite o codigo mudando suas credênciais, do postgres e do Redis, caso não tenha essas dependências instaladas no seu 
Easypanel, instalar antes. 

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
<img width="1029" height="545" alt="image" src="https://github.com/user-attachments/assets/d6b8902e-fb07-4aa3-8869-8edf35c8aeee" />

- Criar apartir de esquema: 
<img width="1007" height="557" alt="image" src="https://github.com/user-attachments/assets/4cfb18c3-ae37-4a94-91e7-a81ec7f451c4" />

- Cola seu schema editado, e clique em criar, é só esperar o n8n subir as dependências e tudo estará funcional.
<img width="521" height="497" alt="image" src="https://github.com/user-attachments/assets/ff54da17-6119-4f36-a863-c939af4cc99d" />

## Caso o seu dê erro revise suas credênciais se preencheu corretamente e tente novamente. 



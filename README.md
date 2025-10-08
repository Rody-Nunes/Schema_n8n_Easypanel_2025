# Este repositório contém um workflow/schema para Easypanel.
exportado do n8n, com todas as dependências, necessárias, em modo Fila e MCP ativo.

## Como instalar:
Copie o Schema que deixamos, abra no seu Programa de edição como cursor, Visual Studio code etc...

Edite o codigo mudando suas credênciais, do postgres e do Redis, caso não tenha essas dependências instaladas no seu Easypanel, instalar antes, para proseguir com o n8n.

## Campos a preencher:

Nome_do_servico_Redis_AQUI: nome serviço Redis criado no Easypanel

Porta_do_Redis_AQUI: porta Redis (geralmente 6379)

Senha_Redis_AQUI: senha Redis definida no Easypanel

Nome_do_servico_Postgres_AQUI: nome serviço Postgres criado no Easypanel

Porta_do_Postgres_AQUI: porta Postgres (geralmente 5432)

Nome_do_Banco_AQUI: nome do banco de dados criado

Usuario_Postgres_AQUI: usuário do banco Postgres

Senha_Postgres_AQUI: senha do usuário Postgres

SUA_CHAVE_ENCRYPTION_AQUI: chave de criptografia n8n (pode gerar com comando ou usar senha segura)

## Depois que preencher com suas credeciais, Siga o tutorial abaixo.

## Clique em Personalizado: 
<img width="1006" height="544" alt="image" src="https://github.com/user-attachments/assets/9593fb8e-916f-4270-8b49-ec98a12049b0" />

## Criar apartir de esquema:
<img width="997" height="469" alt="image" src="https://github.com/user-attachments/assets/5026d740-3e98-45d9-990c-784936e32fe3" />

## Cola seu schema editado, e clique em criar, é só esperar o n8n subir as dependências e tudo estará funcional.
<img width="547" height="486" alt="image" src="https://github.com/user-attachments/assets/392e2376-c77d-4d1a-ae5b-60b44ec6353f" />


## Caso o seu dê erro revise suas credênciais se preencheu corretamente e tente novamente.

------------------------------------------------------------------------------------------------------
## Parabéns agora voccê tem um n8n escalável enterprise !! 

🎉 Resumo: Seu N8N está TURBINADO!
✅ O que seu schema tem de MELHOR:
🚀 1. Modo Fila (Queue Mode) - ATIVO

## Main gerencia a interface e enfileira jobs no Redis
Worker processa execuções em paralelo (concorrência: 10 jobs simultâneos)
Benefícios:
✅ Workflows não travam mais
✅ Execuções pesadas não afetam a interface
✅ Pode escalar horizontalmente (adicionar mais workers)
✅ Alta disponibilidade e performance



🤖 2. MCP (Model Context Protocol) - ATIVO

N8N_MCP_ENABLED=true

O que é: Protocolo para integrar IA/LLMs diretamente no n8n
Benefícios:

✅ Workflows podem usar contexto de IA avançada
✅ Integração nativa com modelos de linguagem
✅ Automações mais inteligentes


⚡ 3. Task Runners - ATIVO

N8N_RUNNERS_ENABLED=true

O que faz: Executa código JavaScript/Python em processos isolados
Benefícios:

✅ Maior segurança (isolamento de código)
✅ Melhor performance para nodes pesados
✅ Previne crashes do processo principal


📊 4. Métricas - ATIVO
N8N_METRICS=true

Benefícios:

✅ Monitore performance em tempo real
✅ Prometheus-compatible metrics
✅ Rastreie uso de recursos


🔄 5. Offload de Execuções Manuais
OFFLOAD_MANUAL_EXECUTIONS_TO_WORKERS=true

O que faz: Até execuções manuais vão para workers
Benefícios:

✅ Interface sempre responsiva
✅ Testes de workflows não sobrecarregam o main


💾 6. Salvamento Completo de Execuções
EXECUTIONS_DATA_SAVE_ON_ERROR=all
EXECUTIONS_DATA_SAVE_ON_SUCCESS=all
EXECUTIONS_DATA_SAVE_MANUAL_EXECUTIONS=true

### Benefícios:

✅ Debug facilitado (histórico completo)
✅ Auditoria total
✅ Replay de execuções


🏥 7. Health Check de Fila
QUEUE_HEALTH_CHECK_ACTIVE=true

### Benefícios:
✅ Monitora saúde do Redis
✅ Detecta problemas automaticamente


🌍 8. Localização Brasileira
GENERIC_TIMEZONE=America/Sao_Paulo
N8N_DEFAULT_LOCALE=pt-BR
TZ=America/Sao_Paulo

✅ Horários corretos (Brasília)
✅ Interface em português
✅ Cron jobs no fuso correto

<img width="529" height="366" alt="image" src="https://github.com/user-attachments/assets/ff6838b2-a480-41f2-b969-3314f9fe6352" />


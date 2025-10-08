## Instalando Esquema Easypanel_n8n_interprise

📋 Pré-requisitos
Antes de começar, você precisará ter o Redis e o postgres isntalado em suas dependencias do Easypanel

criar estes serviços no Easypanel:

1️⃣ Serviço Redis

No Easypanel, crie um novo serviço Redis
Configure uma senha forte
Anote os seguintes dados:

Nome do serviço (ex: meu_redis)
Porta (padrão: 6379)
Senha definida

2️⃣ Serviço PostgreSQL

No Easypanel, crie um novo serviço PostgreSQL
Após criar, acesse o terminal do Postgres e crie um banco de dados:

```
sql   CREATE DATABASE n8n_db;
```

Anote os seguintes dados:

Nome do serviço (ex: meu_postgres)
Porta (padrão: 5432)
Nome do banco criado (ex: n8n_db)
Usuário (padrão: postgres)
Senha definida


3️⃣ Gerar Chave de Criptografia
O N8N precisa de uma chave única de 32 caracter para criptografar dados sensíveis. Escolha uma opção:
https://www.avast.com/random-password-generator#mac

## Editando o esquema, Abra o Esquema.json em um programa edit Dev, como Visual studio code , cursor entre outros....

depois de aberto edite o que pedir, adicionando suas credênciais aonde pedir no esquema: 

### Pontos para Preencher no Template

Substitua os seguintes placeholders no arquivo JSON com suas informações:

- NOME_DO_PROJETO_AQUI → Nome do seu projeto no Easypanel
- NOME_DO_SERVICO_REDIS_AQUI → Nome do serviço Redis criado no Easypanel
- PORTA_DO_REDIS_AQUI → Porta do Redis (geralmente 6379)
- SENHA_REDIS_AQUI → Senha do Redis definida no Easypanel
- NOME_DO_SERVICO_POSTGRES_AQUI → Nome do serviço Postgres criado no Easypanel
- PORTA_DO_POSTGRES_AQUI → Porta do Postgres (geralmente 5432)
- NOME_DO_BANCO_AQUI → Nome do banco de dados criado
- USUARIO_POSTGRES_AQUI → Usuário do banco Postgres
- SENHA_POSTGRES_AQUI → Senha do usuário Postgres
- SUA_CHAVE_ENCRYPTION_AQUI → Chave de criptografia única (32+ caracteres)

## Implementando no Easypainel: 

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

# Arqueterura do n8n atualizado: 
┌──────────────────────────────────────────┐
│           USUÁRIO (Browser)               │
└─────────────┬────────────────────────────┘
              │ HTTPS
              ▼
┌──────────────────────────────────────────┐
│         N8N MAIN (Interface)              │
│  • Gerencia workflows                     │
│  • Enfileira execuções no Redis           │
│  • Task Broker (comunicação interna)      │
│  • MCP habilitado                         │
└─────────────┬────────────────────────────┘
              │
              ▼
┌──────────────────────────────────────────┐
│          REDIS (Fila Bull)                │
│  • Armazena jobs pendentes                │
│  • Gerencia fila de execuções             │
└─────────────┬────────────────────────────┘
              │
              ▼
┌──────────────────────────────────────────┐
│       N8N WORKER (Processador)            │
│  • Processa 10 jobs simultâneos           │
│  • Executa workflows                      │
│  • Task Runners isolados                  │
└─────────────┬────────────────────────────┘
              │
              ▼
┌──────────────────────────────────────────┐
│      POSTGRESQL (Banco de Dados)          │
│  • Workflows e configurações              │
│  • Histórico completo de execuções        │
│  • Credenciais criptografadas            │
└──────────────────────────────────────────┘

------------------------------------------------------------------------------------
## Checklist antes de reportar problemas:

 Redis e Postgres estão com status verde no Easypanel?
 Todos os placeholders foram substituídos no JSON?
 N8N_ENCRYPTION_KEY é idêntica em Main e Worker?
 Logs do Worker mostram "n8n worker is now ready"?
 Testou executar um workflow simples?

 # Use por sua conta e Risco, não oferecemos suporte. 
- Temple Em uso e funcional.
 


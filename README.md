# dotnet-azure-functions-queue

## Objetivo
Processamento assíncrono de tarefas em background. O serviço recebe solicitações via HTTP, publica mensagens em uma fila e processa cada tarefa de forma desacoplada, evitando que o cliente espere por operações demoradas e distribuindo carga ao longo do tempo.

## Stack
- Backend: .NET 8, Azure Functions (Isolated Worker)
- Frontend: N/A (API serverless)
- Banco: N/A (estado em fila)
- Cloud: Azure Functions, Azure Queue Storage
- Testes: xUnit

## Arquitetura
- Serverless
- Event-driven
- SOLID
- Separação de responsabilidades (Trigger, Application, Infrastructure)

## Funcionalidades
- Recebimento de solicitações via HTTP Trigger
- Publicação de mensagens em Azure Queue
- Processamento assíncrono via Queue Trigger
- DTOs para contrato de entrada e mensagem
- Logging estruturado
- Retry automático em caso de falha no consumidor

## Como executar
```bash
docker-compose up -d
func start
```

Envie uma requisição para o endpoint HTTP e acompanhe o processamento nos logs do Queue Trigger.

## Prints
Adicionar imagens das telas.

## Aprendizados demonstrados
- Uso de Azure Functions com HTTP Trigger e Queue Trigger no mesmo host
- Desacoplamento entre produtor e consumidor via fila
- Modelagem de DTOs para transporte de mensagens
- Estratégia de retry e dead-letter em cenários serverless
- Logging e observabilidade em funções isoladas
- Separação clara de responsabilidades entre camadas

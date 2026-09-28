# Visão arquitetural de projetos

Este repositório reúne uma visão uplevel de arquitetura dos principais projetos
com os quais trabalhei nos últimos sete anos.

O objetivo é registrar, de forma visual e objetiva, os principais problemas de
negócio, decisões arquiteturais, integrações, fluxos de processamento, trade-offs
e estratégias de resiliência presentes nesses projetos.

Eles representam uma visão de alto nível, adequada para apresentar o contexto, as
responsabilidades dos componentes e os princípios que orientaram cada solução.

## Projetos

### REC — Grupo Bandeirantes

Plataforma de processamento e publicação de mídia construída para transformar
transmissões ao vivo em cortes publicáveis.

O case aborda:

- processamento distribuído de vídeo em infraestrutura on-premises;
- pipeline assíncrono com RabbitMQ, FFmpeg e workers .NET;
- controle de capacidade física, concorrência e operações de I/O;
- rastreabilidade por Crop UUID;
- reprocessamento localizado, DLQ, idempotência e limpeza de artefatos;
- tratamento de falhas parciais durante a publicação em múltiplos destinos.

- [Arquitetura de processamento de mídia](rec-media-processing-architecture.excalidraw)


### Blaze — Internal Developer Platform

Plataforma interna para criação e execução de automações em um ambiente
bancário, equilibrando autonomia dos times com governança, segurança,
rastreabilidade e auditabilidade.

O case aborda:

- self-service para criadores e consumidores de automações;
- separação entre experiência, orquestração e execução;
- workflows BPMN executados com Camunda;
- comunicação assíncrona com RabbitMQ, incluindo retry, DLQ e idempotência;
- integração com ServiceNow, aprovações e evidências de testes;
- correlação entre estado técnico, estado de governança e auditoria;
- separação de workloads relacionais e documentais entre PostgreSQL e MongoDB.

- [Arquitetura do Blaze IDP](blaze-idp-architecture.excalidraw)

## Organização do repositório

- `*.excalidraw`: diagramas arquiteturais editáveis;


## Nota sobre o nível de detalhe

Os diagramas e apresentações priorizam decisões arquiteturais e relações entre
responsabilidades. Detalhes proprietários, configurações específicas,
credenciais, métricas não públicas e implementações internas não fazem parte
deste repositório.

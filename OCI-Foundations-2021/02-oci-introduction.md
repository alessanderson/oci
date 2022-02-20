# OCI - Introduction

## OCI - Overview

### Categorias:

|                    |              |           |                             |
|--------------------|--------------|-----------|-----------------------------|
| Developer Services | Applications | Analytics | Governance & Administration |
| | Data & AI | Databases | |
| |Infrastructure |
 



### Core Infrastructure Services

- Core Infrastructure
  - Compute
  - Containers
  - OS, VMWare
  - Storage
  - Networking
- Databases
  - Oracle Databases
  - Distributed & OSS Databases
    - NoSQL
    - MySQL
- Data & AI
  - Big Data
  - AI Services
  - Messaging
- Applications
  - Serverless
  - App Integration
  - Business & Industry SaaS
- Analytics
  - Business Analytics
- Developer Services
  - Low Code
  - AppDev
  - IaaS
- Governance & Administration
  - CloudOps
    - IAM
    - Compartments
    - Tagging
    - Cost Advisor
  - Security
    - Cloud Guard
    - Security Zones
    - Vault
    - KMS
    - Data Safe
    - DDoS
    - WAF
  - Observability
    - Monitoring
    - Logging
    - Loggin Analytics
    - Notifications
    - APM
    - Management Clound


## OCI - Architecture

- **`Regiões`**: Área geográfica que contém um ou mais Availability Domains (AD)
  - Existem pelo menos duas regiões em cada país

- **`Availability Domain (AD)`**: Um ou mais datacenters tolerantes a falhas, localizados em uma região e conectados uns aos outros por uma `rede de alta largura de banda e baixa latência`. 
  - Isolados uns dos outros e tolerantes a falhas;
  - Não compartilham infraestrutura física;
  - Cada AD possui 03 (três) fault domains;
> **BIZU**: Protege contra falhas em uma região

- **`Fault Domain`**: Agrupamento de hardware e infraestrutura dentro de um AD, cujo objetivo é fornecer **_antiafinidade_** (permitir a distribuição das instâncias dentro de um AD, para que não fiquem no mesmo hardware físico); 
  - _"Datacenter Lógico"_ dentro de uma AD
  - Recursos alocados em diferentes FDs não compartilham pontos únicos de falha de hardware
> BIZU: Protege contra falhas em um AD 

### Critérios de Escolha de uma Região
- `Localização:` Escolher **a mais próxima dos usuários finais**, para menor latência e maior performance;

- `Residência dos Dados e Compliance:` deve estar em conformidade com os requisitos do país;

- `Disponibilidade do Serviço:` Novos serviços são disponibilizaods com base na demanda, conformidade regulatória, disponibilidade de recursos e outros fatores.

### Como evitar Pontos únicos de falha
- Desenhar uma arquitetura para fazer o deploy de instâncias que que executam as mesmas tarefas
  - (no mesmo AD) em FD diferentes
  - (na mesma região) em AD diferentes
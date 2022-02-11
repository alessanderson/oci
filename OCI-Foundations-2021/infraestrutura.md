# Infraestrutura

- [Fundamentos do Serviço](#fundamentos-do-servico)
- [Compute](#compute)
- [Containers](#containers)
- [OS, VMWare](#os-vmware)
- [Storage](#storage)
- [Networking](#networking)

---

## Fundamentos do Servico
- **`Regiões`**: Área geográfica que contém um ou mais Availability Domains (AD)
  - Existem pelo menos duas regiões em cada país

- **`Availability Domain (AD)`**: Um ou mais datacenters tolerantes a falhas, localizados em uma região e conectados uns aos outros por uma rede de alta largura de banda e baixa latência. 
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
---

## Compute

blablabla

---
## Containers

blablabla

---

## OS, VMWare

blablabla

---

## Networking
blablabla

---
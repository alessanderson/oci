# OCI Security

## Introduction
- Shared Security Model
  - Oracle
    * Virtualização
    * Physical Hosts
    * Physical Network
    * Physical Datacenter

  - Customer
    * Data
    * Devices
    * Accounts & Identities
    * Applications
    * Network Controls
    * Operating System

### Security Line-up


| Use Case | Security Services | Service |
| - | - | - |
| - Manage user access and policies <br> Manage MFA <br> SSO to identity providers | **Identity and Access Management** | IAM | 
|- Encryption for data <br> - Discorvery, classify and protect data <br> - Key storage and management <br> - Rotate, manage and retrieve secrets | **Data Protection** | Encryption / Key Management / Key Vault / Data Safe |
|- Secure Posture Management <br> - Secure Advisor <br> - Secure Enclave <br> - Automated Security Assessment | **Detection and Remediation** [CSPM] | Cloud Guard / Max Security / Vulnerability / Security Advisor | 
| - Patch Management <br> - Workload Isolation <br> - Managed Bastion | **OS And Workload Protection** | Dedicated Host / Bastion / OS Management |
| - Network Security Control <br> - Filter malicious Web Traffic <br> - DDoS Protection | **Infrastructure Protection** | DDoS Protection / WAF / Security Lists | 
|  |  |  |


## Cloud Guard
- Ajuda a monitorar e identificar falhas de segurança em potencial
- Remediação completamente automatizada
* Detectar problemas
   - Checa configurações
   - Monitora atividades
* Aplicar resposta
  - Correlaciona problemas
  - Aplica Fix

### Processo
Target (rescursos a serem analizados) &rarr; Detectors (problemas identificados) &rarr; Problems (possíveis falhas de segurança) &rarr; Responders (notificações/ações corretivas)


## Security Zones e Security Advisor
- Security Zones
  - Refere-se a um compartment no qual a `segurança não pode ser violada`
  - Trata-se de um **conjunto de políticas de segurança** que são associadas a um compartment
  - A politica é aplicada `no momento de criação do recurso`
  * Suportado pelos principais recursos primitivos: rede, storage, compute e database
- Security Advisor
  - **`Unifica` a security zone, cloud guard e outros recursos de modo coeso.**
  * Suportado pelo object storage, file storage, block volumes e VMs


## Vulnerability Scanning
- Checa rotireiramente os hosts quanto a possiveis vulnerabilidades (CVE)
- Scanning recipes
  * Frequencia (diaria/semanal)
  * Port Scanning
  * Agent Based Scanning: check against standard benchmarks (CIS)
    - Risk Levels

## Vault
- Gerencia credenciais secretas (passwords) e chaves de criptografia (key)
- Remove a necessidade de chaves e secrets estarem espostas no código ou em arquivos de configuração
  - Key: como transformar texto simples em texto cifrado na criptografia e vice versa
  - Secrets: credenciais tipo senhas, certificados, chaves SSH ou tokens
- Dois tipos de proteção
  - Software
    - Armazenada no servidor
    - Pode ser exportada para executar operações no cliente, em vez de no servidor
  - HSM (hardware Security Module)
    - Master security key armazenada no dispositivo de HSM e `não pode ser exportada`
    - Todas as operações criptográficas acontecem no HSM
- Algoritmos AES, RSA e ECDSA
- Chaves integradas na OCI
- Rotação de master keys
- Serviço regional

### Conceitos básicos das Chaves
- Hierarquia Two-Tiered (Envelope Encryption)
  - As `master keys` encriptam as `chaves de dados`. Essas são as efetivamente usadas na criptografia dos recursos
- Key Vault protegido por policies e auditing
- Benefícios:
  - Fácil de gerenciar
  - Limita o raio de explosão ?
  - Não gera uma completa re-criptografia dos dados
> **se a master key for excluída, não haverá como recuperar os dados**
- recomendado um periodo de 7-30 day gap
- depois que o vault é excluído, não poderá ser recuperado

## WAF

- Protege contra ataques de camada 7: SQL injections, XSS Exploits, etc
- Aplica um conjunto de regras ao tráfego HTTP/HTTPS
- Permite auditorias e bloqueios de requisições
- Mais de 250 regras ja prontas
- Controles de acesso podem ser customizados: geolocation, IP whitelists, etc
- Suporte multi-cloud


## Bastion
- Serviço gerenciado provisionado dentro da nuvem virtual
- Fornece conectividade RDP/SSH segura e simples com as VM diretamente
- Integração com o IAM
- CIDR block allow list
- Disponibilizado sem custo

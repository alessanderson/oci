# OCI Storage

## Introduction

## Object Storage


## Block Volume

### Tiers

- Basic
  - Large Sequential I/O Workloads
  * `2 IOPS/GB`
- Balanced
  - Balanced choice for Random I/O
  * `60 IOPS/GB`
- Higher Performance
  - Most I/O Demaning workloads
  * `75 IOPS/GB`
- Ultra Higher Performance
  - Highest I/O demaning workloads
  * `90 - 225 IOPS/GB`

** Auto Tune Performance**: reduz o desenpenho do volume para reduzir custo quando o volume está `detached`. Quando o volume é reanexado ele automaticamente é ajustado para a configuração anterior.

Encrypted Block Volumes: volumes criptografados por padrão
- Chaves pela OCI ou pelo cliente
- Criptografia em trânsito

Read/Write Shareable: um unico disco pode ser compartilhado com várias VM 

Resizing Block Volumes: volumes podem ser redimensionados de forma online ou offline

Block Volume Replication: volumes são replicados entre regiões
- Replicação assíncrona

Volume Groups: agrupamento de volumes para facilitar o gerenciamento
- Time Consistant Backups
- Backup de multiplos volumes em multiplas instâncias
- Restauração de todo o grupo de uma vez

Attach to Instance
- ISCSI
- Paravirtualized

Access Type
- Read/Write: anexado a uma unica instância e não compartilhável (default)
- Read/Write - Shareable: anexado a varias instâncias.
  * deve ter configurado um clustered file system para evitar corrupção de dados
- Read Only - Shareable: anexado a multiplas instâncias, mas somente leitura.


## File Storage

- 



## Migration Services
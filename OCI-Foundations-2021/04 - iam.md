# OCI IAM

- IAM: Identity and Access Management Service
- Conceitos:
  -  fornece recursos de `gerenciamento de identidade` e acesso como autenticação, single sign-on (SSO) e gerenciamento do ciclo de vida de identidades
  - `Users`: Um funcionário individual ou sistema que precisa gerenciar ou usar os recursos
  - Principals:
  - `Groups`: Um conjunto de usuários que `precisam do mesmo tipo de acesso` a um conjunto específico de recursos ou compartimento
  - `Dynamic Groups`: Um tipo especial de grupo que contém `recursos que correspondem à regras previamente definidas` (pode ser alterada dinamicamente à medida que os recursos correspondentes são criados ou excluídos)
  - `Policies`: conjunto de regras que especifica quem pode acessar quais recursos e como
  - `Compartments`: conjunto de `recursos relacionados`, usados para **organizar** e **isolar** recursos na nuvem. Usados para separar claramente recursos para fins de medição de uso e faturamento, acesso (pelo uso das políticas) e isolamento.
  - `Resources`: objetos de nuvem que os usuários criam e usam ao interagir com a OCI
  - `Federation`: Uma relação na qual um administrador configura entre um provedor de identidades e um provedor de serviços
  - `Network Sources`: Um g`rupo de endereços IP com permissão` para acessar recursos
  
 Users -> Groups -> Policies -> Compartments -> Resources

 
 - Identificação de um OCI Resource: `OUID`
   - ouid1.<resource type>.<realm>.<region>.<unique ID>
   - Ex: Tenancy: ocid1.tenancy.oc1..aaaaaaaavngx7ytfdfdrri7ll7obcj7dn7cipb3sfbbb6za7rh2ds4swlzbbq
   - Ex: Instance: ocid1.instance.oc1.iad.anuwcljs5yo36aycelboye2ivvcgbnj3ze3m76h6oy42zvfvkekxctaq
   



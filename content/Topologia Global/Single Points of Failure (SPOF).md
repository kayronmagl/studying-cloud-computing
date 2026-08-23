SPOF é um ponto único de falha. Se ele falha, o sistema inteiro ou uma função crítica deixa de operar.

A nuvem oferece recursos para reduzir SPOFs, como [[High Availability]], múltiplas [[Availability Zones (AZ)]] e [[Failover]], mas o cliente precisa desenhar a arquitetura para usá-los. Hospedar uma aplicação na AWS não remove automaticamente componentes únicos e indispensáveis.

---

## O que é

Single Points of Failure (SPOF) deve ser entendido pela posição dos recursos no mapa da nuvem: região, zona, borda, distância, isolamento e dependências. Topologia explica onde as coisas ficam e como falhas ou latência se propagam.

---

## Por que existe

Single Points of Failure (SPOF) existe para explicar como localização, distância, redundância, cache, conectividade e distribuição geográfica afetam disponibilidade, latência, recuperação e custo.

---

## Como funciona

**Onde SPOFs aparecem**

Um SPOF pode ser uma única instância, um único banco, uma única regra de roteamento, uma credencial, uma configuração centralizada, uma dependência externa ou uma equipe/processo sem alternativa operacional.

**Decisão Arquitetural**

Ao escolher região, zona ou estratégia de recuperação, a equipe precisa equilibrar:

* latência para usuários;
* custo;
* conformidade legal;
* disponibilidade desejada;
* complexidade operacional;
* tolerância à perda de dados.

Não basta “usar AWS”. É necessário desenhar onde e como os recursos serão distribuídos.

---

## Exemplo prático

Uma aplicação pode ter duas instâncias em zonas diferentes e ainda possuir um SPOF se ambas dependem de um único banco sem failover, uma única regra de roteamento, uma credencial expirada ou uma configuração centralizada.

Esse desenho depende de conceitos como isolamento, latência, failover, replicação e estado da aplicação.

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Esse desenho reduz alguns SPOFs, mas ainda precisa verificar dependências compartilhadas, capacidade restante, dados e configuração de failover.

---

## Diferenças importantes

Compare Single Points of Failure (SPOF) com região, zona de disponibilidade, edge location, data center, failover e disaster recovery. Cada termo descreve um nível diferente de localização, isolamento ou resposta a falha.

---

## Cuidados

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

---

## Relação com outras notas

- [[High Availability]]
- [[Availability Zones (AZ)]]
- [[Failover]]

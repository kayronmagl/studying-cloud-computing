Isolamento de Falhas limita o impacto de uma falha para que ela não se espalhe por todo o sistema. [[Availability Zones (AZ)]] são desenhadas como limites de isolamento físico e operacional dentro de uma região.

---

## O que é

Isolamento de Falhas deve ser entendido pela posição dos recursos no mapa da nuvem: região, zona, borda, distância, isolamento e dependências. Topologia explica onde as coisas ficam e como falhas ou latência se propagam.

---

## Por que existe

Isolamento de Falhas existe para explicar como localização, distância, redundância, cache, conectividade e distribuição geográfica afetam disponibilidade, latência, recuperação e custo.

---

## Como funciona

**Limites do isolamento**

Isolamento não significa independência absoluta. Componentes em zonas diferentes ainda podem compartilhar dependências regionais, configuração, credenciais, serviços externos, pipelines de deploy ou dados mal replicados.

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

Uma aplicação pode executar instâncias em duas zonas de disponibilidade para reduzir dependência de uma única instalação física. Para que isso funcione em uma falha real, o balanceamento, os dados, a capacidade e as dependências compartilhadas também precisam estar preparados.

Esse desenho depende de conceitos como isolamento, latência, failover, replicação e estado da aplicação.

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Esse desenho usa isolamento de falhas para reduzir impacto zonal, mas precisa de health checks, capacidade restante, recuperação de dados e testes.

---

## Diferenças importantes

Compare Isolamento de Falhas com região, zona de disponibilidade, edge location, data center, failover e disaster recovery. Cada termo descreve um nível diferente de localização, isolamento ou resposta a falha.

---

## Cuidados

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

---

## Relação com outras notas

- [[Availability Zones (AZ)]]

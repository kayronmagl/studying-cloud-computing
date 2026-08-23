Variabilidade de Custos é a mudança de preço conforme região, serviço, uso, armazenamento, tráfego e modelo de compra.

---

## O que é

Variabilidade de Custos deve ser entendido pela posição dos recursos no mapa da nuvem: região, zona, borda, distância, isolamento e dependências. Topologia explica onde as coisas ficam e como falhas ou latência se propagam.

---

## Por que existe

Variabilidade de Custos existe para explicar como localização, distância, redundância, cache, conectividade e distribuição geográfica afetam disponibilidade, latência, recuperação e custo.

---

## Como funciona

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

Uma aplicação pode executar instâncias em duas zonas de disponibilidade. Se uma zona sofrer falha, o tráfego pode ser direcionado para recursos saudáveis em outra zona.

Esse desenho depende de conceitos como isolamento, latência, failover, replicação e estado da aplicação.

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Se um componente falhar, o tráfego deve continuar indo para partes saudáveis.

---

## Diferenças importantes

Compare Variabilidade de Custos com região, zona de disponibilidade, edge location, data center, failover e disaster recovery. Cada termo descreve um nível diferente de localização, isolamento ou resposta a falha.

---

## Cuidados

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

---

## Relação com outras notas

- [[O que é computação em nuvem]]
- [[Regions (Regiões)]]
- [[Availability Zones (AZ)]]
- [[Edge Locations]]

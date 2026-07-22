Isolamento de Falhas limita o impacto de uma falha para que ela não se espalhe por todo o sistema. [[Availability Zones (AZ)]] são desenhadas como limites de isolamento físico e operacional dentro de uma região.

---

## Visão geral

Isolamento de Falhas é uma ideia de localização, falha ou distribuição. Quando estudar, pergunte: “onde o recurso fica?” e “o que acontece se uma parte falhar?”.

Esse raciocínio é essencial para entender alta disponibilidade, disaster recovery e latência.

Isolamento não significa independência absoluta. Componentes em zonas diferentes ainda podem compartilhar dependências regionais, configuração, credenciais, serviços externos, pipelines de deploy ou dados mal replicados.

---

## Exemplo Prático

Uma aplicação pode executar instâncias em duas zonas de disponibilidade para reduzir dependência de uma única instalação física. Para que isso funcione em uma falha real, o balanceamento, os dados, a capacidade e as dependências compartilhadas também precisam estar preparados.

Esse desenho depende de conceitos como isolamento, latência, failover, replicação e estado da aplicação.

---

## Decisão Arquitetural

Ao escolher região, zona ou estratégia de recuperação, a equipe precisa equilibrar:

* latência para usuários;
* custo;
* conformidade legal;
* disponibilidade desejada;
* complexidade operacional;
* tolerância à perda de dados.

Não basta “usar AWS”. É necessário desenhar onde e como os recursos serão distribuídos.

---

## Exemplo Arquitetural

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Esse desenho usa isolamento de falhas para reduzir impacto zonal, mas precisa de health checks, capacidade restante, recuperação de dados e testes.

---

## Cuidados importantes

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

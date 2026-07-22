SPOF é um ponto único de falha. Se ele falha, o sistema inteiro ou uma função crítica deixa de operar.

A nuvem oferece recursos para reduzir SPOFs, como [[High Availability]], múltiplas [[Availability Zones (AZ)]] e [[Failover]], mas o cliente precisa desenhar a arquitetura para usá-los. Hospedar uma aplicação na AWS não remove automaticamente componentes únicos e indispensáveis.

---

## Visão geral

Single Points of Failure (SPOF) é uma ideia de localização, falha ou distribuição. Quando estudar, pergunte: “onde o recurso fica?” e “o que acontece se uma parte falhar?”.

Esse raciocínio é essencial para entender alta disponibilidade, disaster recovery e latência.

Um SPOF pode ser uma única instância, um único banco, uma única regra de roteamento, uma credencial, uma configuração centralizada, uma dependência externa ou uma equipe/processo sem alternativa operacional.

---

## Exemplo Prático

Uma aplicação pode ter duas instâncias em zonas diferentes e ainda possuir um SPOF se ambas dependem de um único banco sem failover, uma única regra de roteamento, uma credencial expirada ou uma configuração centralizada.

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

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Esse desenho reduz alguns SPOFs, mas ainda precisa verificar dependências compartilhadas, capacidade restante, dados e configuração de failover.

---

## Cuidados importantes

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

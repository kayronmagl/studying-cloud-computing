Failover é a transferência da operação para um recurso, zona ou região alternativa após uma falha ou uma condição definida. É central para [[High Availability]] e [[Disaster Recovery (DR)]], mas não acontece sem mecanismos configurados para detectar a falha e mudar o tráfego ou a função do componente.

---

## O que é

Failover deve ser entendido pela posição dos recursos no mapa da nuvem: região, zona, borda, distância, isolamento e dependências. Topologia explica onde as coisas ficam e como falhas ou latência se propagam.

---

## Por que existe

Failover existe para explicar como localização, distância, redundância, cache, conectividade e distribuição geográfica afetam disponibilidade, latência, recuperação e custo.

---

## Como funciona

**Etapas**

Um failover pode envolver:

* detecção por [[Health Checks]];
* decisão de failover;
* alteração de roteamento;
* remoção de destinos não saudáveis;
* promoção de uma réplica;
* recuperação de conexões;
* capacidade suficiente no destino;
* verificação de consistência dos dados;
* retorno ao ambiente original, conhecido como failback;
* testes periódicos.

Nem toda arquitetura usa todas essas etapas, mas ignorá-las costuma gerar falsa sensação de recuperação.

**Failover não é replicação**

Replicação copia ou sincroniza dados entre componentes. Failover transfere a operação para um destino alternativo.

Uma aplicação pode ter dados replicados e ainda não ter failover automático. Também pode redirecionar tráfego para um destino sem dados atualizados, o que causa erros ou perda de consistência.

**Decisão Arquitetural**

Ao escolher região, zona ou estratégia de recuperação, a equipe precisa equilibrar:

* latência para usuários;
* custo;
* conformidade legal;
* disponibilidade desejada;
* complexidade operacional;
* tolerância à perda de dados.

Não basta “usar AWS”. É necessário desenhar onde e como os recursos serão distribuídos.

**Dados alinhados antes da troca**

[[Replicação Síncrona]] ajuda a entender cenários em que dados precisam ser mantidos alinhados antes de um failover.

**Estado da aplicação**

O [[State (Computação)]] influencia failover porque sistemas com estado precisam preservar sessão, dados ou andamento do processamento.

---

## Exemplo prático

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Se um componente falhar, o tráfego pode ser direcionado para partes saudáveis quando health checks, roteamento e capacidade estiverem configurados corretamente.

Mesmo assim, podem ocorrer reconexões, repetição de operações, perda de sessão, degradação temporária e tempo de recuperação.

---

## Diferenças importantes

Compare Failover com região, zona de disponibilidade, edge location, data center, failover e disaster recovery. Cada termo descreve um nível diferente de localização, isolamento ou resposta a falha.

---

## Cuidados

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

---

## Relação com outras notas

- [[High Availability]]
- [[Disaster Recovery (DR)]]
- [[Health Checks]]
- [[Replicação Síncrona]]
- [[State (Computação)]]

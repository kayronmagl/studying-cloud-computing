Falhas Correlacionadas ocorrem quando vários componentes falham pela mesma causa. Separar recursos entre [[Availability Zones (AZ)]] reduz alguns riscos físicos, mas não elimina falhas causadas por dependências compartilhadas.

---

## O que é

Falhas Correlacionadas deve ser entendido pela posição dos recursos no mapa da nuvem: região, zona, borda, distância, isolamento e dependências. Topologia explica onde as coisas ficam e como falhas ou latência se propagam.

---

## Por que existe

Falhas Correlacionadas existe para explicar como localização, distância, redundância, cache, conectividade e distribuição geográfica afetam disponibilidade, latência, recuperação e custo.

---

## Como funciona

**Dependências compartilhadas**

Duas instâncias em AZs diferentes podem falhar juntas se recebem a mesma configuração incorreta, dependem do mesmo banco indisponível, usam uma credencial expirada, são afetadas pelo mesmo deploy defeituoso ou dependem de um serviço externo único.

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

Uma aplicação pode executar instâncias em duas zonas de disponibilidade e ainda falhar por completo se um deploy defeituoso for aplicado nas duas, se o banco central ficar indisponível ou se uma política de permissão impedir todas as instâncias de acessar uma dependência essencial.

Esse desenho depende de conceitos como isolamento, latência, failover, replicação e estado da aplicação.

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Isso reduz falhas locais, mas ainda exige análise de dependências compartilhadas, limites regionais, configuração e processos operacionais.

---

## Diferenças importantes

Compare Falhas Correlacionadas com região, zona de disponibilidade, edge location, data center, failover e disaster recovery. Cada termo descreve um nível diferente de localização, isolamento ou resposta a falha.

---

## Cuidados

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

---

## Relação com outras notas

- [[Availability Zones (AZ)]]

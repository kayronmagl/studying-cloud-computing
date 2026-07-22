Falhas Correlacionadas ocorrem quando vários componentes falham pela mesma causa. Separar recursos entre [[Availability Zones (AZ)]] reduz alguns riscos físicos, mas não elimina falhas causadas por dependências compartilhadas.

---

## Dependências compartilhadas

Duas instâncias em AZs diferentes podem falhar juntas se recebem a mesma configuração incorreta, dependem do mesmo banco indisponível, usam uma credencial expirada, são afetadas pelo mesmo deploy defeituoso ou dependem de um serviço externo único.

---

## Exemplo Prático

Uma aplicação pode executar instâncias em duas zonas de disponibilidade e ainda falhar por completo se um deploy defeituoso for aplicado nas duas, se o banco central ficar indisponível ou se uma política de permissão impedir todas as instâncias de acessar uma dependência essencial.

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

## Exemplo

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Isso reduz falhas locais, mas ainda exige análise de dependências compartilhadas, limites regionais, configuração e processos operacionais.

---

## Cuidados importantes

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

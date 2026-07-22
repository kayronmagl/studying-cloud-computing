Arquitetura Multi-Region distribui componentes entre múltiplas [[Regions (Regiões)|regiões]] AWS.

Ela é usada quando requisitos de recuperação de desastre regional, baixa latência global, residência de dados, conformidade ou continuidade de negócios justificam maior isolamento geográfico.


Multi-Region não é prática obrigatória para toda aplicação. Muitas necessidades de disponibilidade podem ser atendidas dentro de uma única região com [[Arquitetura Multi-AZ]], desde que a aplicação, os dados e a rede estejam bem desenhados.

Operar em várias regiões aumenta significativamente a complexidade. Failover entre regiões não acontece apenas porque recursos existem em mais de uma região. A estratégia precisa definir replicação, roteamento, consistência, capacidade, observabilidade, permissões, testes e operação.


---

## Diferença para Multi-AZ

[[Arquitetura Multi-AZ]] distribui recursos entre zonas dentro de uma região.

Multi-Region distribui recursos entre regiões diferentes.

---

## Benefícios

* tolerância a falhas regionais;
* menor latência para usuários globais;
* residência de dados;
* continuidade de negócio;
* estratégia avançada de disaster recovery.

---

## Desafios

* replicação de dados;
* consistência;
* latência entre regiões;
* DNS;
* failover;
* custo;
* transferência entre regiões;
* duplicação de capacidade;
* observabilidade;
* operação;
* deploy;
* segurança;
* testes;
* recuperação do ambiente primário.

---

## Serviços Relacionados

* [[Amazon Route 53]];
* [[Route 53 Health Checks]];
* [[Failover Routing]];
* [[Amazon S3]] replication;
* bancos com replicação global quando aplicável;
* [[Amazon CloudWatch]];
* [[AWS CloudTrail]].

---

## Failover entre regiões

Um desenho Multi-Region precisa definir como o tráfego muda de uma região para outra. Isso pode envolver [[Amazon Route 53]], [[Route 53 Health Checks]], [[Failover Routing]] ou outros mecanismos de roteamento.

Também é necessário garantir que a região secundária tenha dados, capacidade e dependências suficientes para assumir a carga. Se os dados não forem replicados corretamente, o tráfego pode ser direcionado para um ambiente vazio, atrasado ou inconsistente.

Depois da recuperação, a equipe ainda precisa decidir como ocorrerá o failback, ou seja, o retorno para o ambiente primário ou para uma nova região principal.

---

## Cuidado

Multi-Region é poderoso, mas complexo.

Não deve ser usado apenas por parecer sofisticado. Deve responder a requisitos reais de RTO, RPO, latência ou conformidade.

---

## Cuidados importantes

Multi-Region pode melhorar continuidade e alcance, mas traz trade-offs de consistência, latência, residência de dados, custo, transferência entre regiões, duplicação de ambientes, testes de failover e operação diária.

Não trate Multi-Region como equivalente a Multi-AZ. Multi-AZ trabalha dentro de uma região; Multi-Region atravessa limites geográficos independentes.

---

## Como entender isso

Este conceito pertence ao módulo de escalabilidade e alta disponibilidade.

## Ponto central

Multi-Region distribui recursos entre regiões diferentes. Ela não substitui Multi-AZ; atende requisitos de isolamento geográfico, recuperação regional, latência global ou conformidade quando esses requisitos justificam a complexidade.

## Como Diferenciar

* Multi-AZ reduz impacto de falha zonal dentro de uma região.
* Multi-Region reduz dependência de uma única região, mas exige replicação, roteamento, capacidade e operação em mais de um local.
* RTO e RPO ajudam a decidir se Multi-Region é necessário.
* Health checks e roteamento podem participar do failover, mas não substituem dados consistentes nem ambiente secundário preparado.

## Cuidado importante

Auto Scaling não garante alta disponibilidade sozinho. Em Multi-Region, além de escala local, a arquitetura precisa de roteamento, replicação, observabilidade, permissões, capacidade e processo operacional em cada região envolvida.

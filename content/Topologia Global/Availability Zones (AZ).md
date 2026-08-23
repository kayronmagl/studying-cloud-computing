Uma Availability Zone, ou AZ, é um local fisicamente separado dentro de uma [[Regions (Regiões)|região da AWS]].

Uma AZ contém um ou mais [[Data Centers|data centers]] com energia, rede e conectividade redundantes. As zonas de uma mesma região são interligadas por redes privadas redundantes, de alta largura de banda e baixa latência.

A quantidade de AZs varia entre regiões e pode mudar. Quando a quantidade atual for relevante para uma decisão, consulte a documentação oficial da AWS em vez de tratar um número como característica permanente.

---

## O que é

Availability Zones (AZ) deve ser entendido pela posição dos recursos no mapa da nuvem: região, zona, borda, distância, isolamento e dependências. Topologia explica onde as coisas ficam e como falhas ou latência se propagam.

---

## Por que existe

Availability Zones (AZ) existe para explicar como localização, distância, redundância, cache, conectividade e distribuição geográfica afetam disponibilidade, latência, recuperação e custo.

---

## Como funciona

**Por que as AZs Existem**

A separação reduz a chance de um único evento físico afetar toda a região. Incêndio, falha elétrica, inundação ou problema de conectividade podem atingir uma zona sem necessariamente interromper as demais.

Isso não significa independência absoluta. [[Falhas Correlacionadas]] ainda podem ocorrer quando aplicações compartilham dependências regionais, configurações incorretas ou componentes centralizados.

Por isso, AZ deve ser entendida como limite de isolamento de falhas, não como garantia automática de continuidade. A aplicação precisa distribuir componentes, dados e capacidade de forma coerente para aproveitar esse isolamento.

**Recursos Zonais e Regionais**

Subnets pertencem a uma única AZ. Instâncias [[Amazon EC2|EC2]] e volumes EBS também são criados em zonas específicas.

Serviços regionais podem distribuir ou replicar componentes entre várias zonas. Alguns serviços gerenciados usam múltiplas AZs internamente; outros recursos exigem configuração explícita do cliente. A arquitetura precisa entender essa diferença para não assumir que um recurso zonal já possui redundância automática.

**Alta Disponibilidade**

Executar componentes em várias AZs é uma das bases da [[High Availability|alta disponibilidade]] na AWS. Normalmente isso envolve balanceamento de carga, health checks, capacidade em mais de uma zona e bancos configurados para failover.

Múltiplas AZs reduzem o impacto de uma falha zonal, mas não substituem backups, observabilidade, testes, planejamento de recuperação e desenho de aplicação tolerante a reconexões, degradação e falhas parciais.

---

## Exemplo prático

Em uma arquitetura simples, usuário, aplicação, rede, banco, armazenamento, segurança e monitoramento trabalham juntos. Availability Zones (AZ) deve ser entendido pelo papel que exerce nesse conjunto.

---

## Diferenças importantes

Compare Availability Zones (AZ) com região, zona de disponibilidade, edge location, data center, failover e disaster recovery. Cada termo descreve um nível diferente de localização, isolamento ou resposta a falha.

---

## Cuidados

O cuidado principal em Availability Zones (AZ) é confundir estar distribuído com estar resiliente. Resiliência exige teste, capacidade, dados recuperáveis, roteamento correto e objetivos claros de RTO e RPO.

---

## Relação com outras notas

- [[Regions (Regiões)]]
- [[Data Centers]]
- [[Falhas Correlacionadas]]
- [[High Availability]]

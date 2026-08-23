Uma região da AWS é uma área geográfica independente que contém múltiplas [[Availability Zones (AZ)|Zonas de Disponibilidade]].

A quantidade de AZs varia entre regiões e pode mudar ao longo do tempo. Quando um número atual for importante, ele deve ser verificado na documentação oficial da AWS. Para entender o conceito, o ponto principal é que a região agrupa zonas fisicamente separadas, conectadas por redes privadas redundantes, de alta capacidade e baixa latência.

---

## O que é

Regions (Regiões) deve ser entendido pela posição dos recursos no mapa da nuvem: região, zona, borda, distância, isolamento e dependências. Topologia explica onde as coisas ficam e como falhas ou latência se propagam.

---

## Por que existe

Regions (Regiões) existe para explicar como localização, distância, redundância, cache, conectividade e distribuição geográfica afetam disponibilidade, latência, recuperação e custo.

---

## Como funciona

**O que é Regional**

Alguns recursos existem dentro de uma região e podem utilizar várias zonas. Outros são zonais e pertencem a uma AZ específica.

A escolha da região influencia:

* [[Latência]] para usuários e sistemas externos;
* disponibilidade de serviços e tipos de recurso;
* custos e modelos de cobrança;
* requisitos legais, residência e soberania de dados;
* [[Conformidade Legal]];
* estratégias de recuperação;
* continuidade de negócios;
* proximidade de usuários, [[APIs|APIs]], parceiros e sistemas dependentes;
* [[Custo de Transferência de Dados|custo de transferência]] entre regiões.

Proximidade geográfica é apenas um critério. Uma região próxima pode reduzir latência, mas a decisão também precisa considerar disponibilidade dos serviços necessários, requisitos regulatórios, custo, capacidade operacional e dependências externas.

**Isolamento entre Regiões**

Regiões são limites importantes de isolamento. Recursos e dados criados em uma região não aparecem automaticamente em outra. Replicação e cópia precisam ser configuradas quando a arquitetura exige recuperação regional ou presença global.

Uma arquitetura multi-região pode aumentar isolamento geográfico e alcance, mas também aumenta custo, complexidade operacional, necessidade de automação, dificuldade de manter dados consistentes e esforço de teste. Ela não deve ser tratada como requisito padrão para toda aplicação.

**Região não é Zona**

A região representa a área geográfica. A AZ representa um domínio de falha dentro dela. Distribuir recursos entre AZs aumenta a [[High Availability|alta disponibilidade]] diante de falhas zonais; distribuir entre regiões atende cenários mais amplos de continuidade, latência ou soberania de dados.

Também não é correto dizer que uma região é onde todas as partes da aplicação vivem. Uma aplicação pode usar recursos em uma única região, em várias regiões ou combinar recursos regionais com serviços globais, dependendo da arquitetura e dos requisitos.

---

## Exemplo prático

Em uma arquitetura simples, usuário, aplicação, rede, banco, armazenamento, segurança e monitoramento trabalham juntos. Regions (Regiões) deve ser entendido pelo papel que exerce nesse conjunto.

---

## Diferenças importantes

Compare Regions (Regiões) com região, zona de disponibilidade, edge location, data center, failover e disaster recovery. Cada termo descreve um nível diferente de localização, isolamento ou resposta a falha.

---

## Cuidados

O cuidado principal em Regions (Regiões) é confundir estar distribuído com estar resiliente. Resiliência exige teste, capacidade, dados recuperáveis, roteamento correto e objetivos claros de RTO e RPO.

---

## Relação com outras notas

- [[Availability Zones (AZ)]]
- [[Latência]]
- [[Conformidade Legal]]
- [[Custo de Transferência de Dados]]
- [[High Availability]]

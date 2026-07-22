Uma região da AWS é uma área geográfica independente que contém múltiplas [[Availability Zones (AZ)|Zonas de Disponibilidade]].

A quantidade de AZs varia entre regiões e pode mudar ao longo do tempo. Quando um número atual for importante, ele deve ser verificado na documentação oficial da AWS. Para entender o conceito, o ponto principal é que a região agrupa zonas fisicamente separadas, conectadas por redes privadas redundantes, de alta capacidade e baixa latência.

---

## O que é Regional

Alguns recursos existem dentro de uma região e podem utilizar várias zonas. Outros são zonais e pertencem a uma AZ específica.

A escolha da região influencia:

* [[Latência]] para usuários e sistemas externos;
* disponibilidade de serviços e tipos de recurso;
* custos e modelos de cobrança;
* requisitos legais, residência e soberania de dados;
* [[Conformidade Legal]];
* estratégias de recuperação;
* continuidade de negócios;
* proximidade de usuários, APIs, parceiros e sistemas dependentes;
* [[Custo de Transferência de Dados|custo de transferência]] entre regiões.

Proximidade geográfica é apenas um critério. Uma região próxima pode reduzir latência, mas a decisão também precisa considerar disponibilidade dos serviços necessários, requisitos regulatórios, custo, capacidade operacional e dependências externas.

---

## Isolamento entre Regiões

Regiões são limites importantes de isolamento. Recursos e dados criados em uma região não aparecem automaticamente em outra. Replicação e cópia precisam ser configuradas quando a arquitetura exige recuperação regional ou presença global.

Uma arquitetura multi-região pode aumentar isolamento geográfico e alcance, mas também aumenta custo, complexidade operacional, necessidade de automação, dificuldade de manter dados consistentes e esforço de teste. Ela não deve ser tratada como requisito padrão para toda aplicação.

---

## Região não é Zona

A região representa a área geográfica. A AZ representa um domínio de falha dentro dela. Distribuir recursos entre AZs aumenta a [[High Availability|alta disponibilidade]] diante de falhas zonais; distribuir entre regiões atende cenários mais amplos de continuidade, latência ou soberania de dados.

Também não é correto dizer que uma região é onde todas as partes da aplicação vivem. Uma aplicação pode usar recursos em uma única região, em várias regiões ou combinar recursos regionais com serviços globais, dependendo da arquitetura e dos requisitos.

Uma região da AWS é uma área geográfica independente que contém várias [[Availability Zones (AZ)|Zonas de Disponibilidade]].

Cada região possui pelo menos três AZs. Elas são conectadas por redes privadas de alta capacidade e baixa latência, mas permanecem fisicamente separadas para reduzir o impacto de falhas locais.

---

## O que é Regional

Alguns recursos existem dentro de uma região e podem utilizar várias zonas. Outros são zonais e pertencem a uma AZ específica.

A escolha da região influencia:

* [[Latência]] para usuários e sistemas externos;
* disponibilidade de serviços e tipos de recurso;
* preço;
* requisitos legais e residência de dados;
* estratégias de recuperação;
* custo de transferência entre regiões.

---

## Isolamento entre Regiões

Regiões são limites importantes de isolamento. Recursos e dados criados em uma região não aparecem automaticamente em outra. Replicação e cópia precisam ser configuradas quando a arquitetura exige recuperação regional ou presença global.

Uma arquitetura multi-região pode aumentar disponibilidade e alcance, mas também aumenta custo, complexidade operacional e dificuldade de manter dados consistentes.

---

## Região não é Zona

A região representa a área geográfica. A AZ representa um domínio de falha dentro dela. Distribuir recursos entre AZs aumenta a [[High Availability|alta disponibilidade]] diante de falhas zonais; distribuir entre regiões atende cenários mais amplos de continuidade, latência ou soberania de dados.

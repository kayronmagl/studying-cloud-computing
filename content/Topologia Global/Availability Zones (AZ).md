Uma Availability Zone, ou AZ, é um local fisicamente separado dentro de uma [[Regions (Regiões)|região da AWS]]. Cada região possui pelo menos três AZs.

Uma AZ contém um ou mais datacenters com energia, rede e conectividade redundantes. As zonas de uma mesma região são interligadas por rede privada de alta capacidade e baixa latência.

---

## Por que as AZs Existem

A separação reduz a chance de um único evento físico afetar toda a região. Incêndio, falha elétrica, inundação ou problema de conectividade podem atingir uma zona sem necessariamente interromper as demais.

Isso não significa independência absoluta. [[Falhas Correlacionadas]] ainda podem ocorrer quando aplicações compartilham dependências regionais, configurações incorretas ou componentes centralizados.

---

## Recursos Zonais e Regionais

Subnets pertencem a uma única AZ. Instâncias EC2 e volumes EBS também são criados em zonas específicas.

Serviços regionais podem distribuir ou replicar componentes entre várias zonas. A arquitetura precisa entender essa diferença para não assumir que um recurso zonal já possui redundância automática.

---

## Alta Disponibilidade

Executar componentes em várias AZs é uma das bases da [[High Availability|alta disponibilidade]] na AWS. Normalmente isso envolve balanceamento de carga, health checks, capacidade em mais de uma zona e bancos configurados para failover.

Múltiplas AZs reduzem o impacto de uma falha zonal, mas não substituem backups, observabilidade, testes e planejamento de recuperação.

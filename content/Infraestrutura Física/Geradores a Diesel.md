Geradores a Diesel fornecem energia durante falhas prolongadas. Em data centers, complementam UPS e redes elétricas redundantes.

---

## Visão geral

Pense em Geradores a Diesel como a parte que normalmente fica invisível para quem usa nuvem. Você não administra isso diretamente, mas esse conceito explica por que existem regiões, zonas, redundância e preocupação com disponibilidade.

Não pule esta nota: ela ajuda a lembrar que “nuvem” continua dependendo de infraestrutura real.

---

## Por que Importa para AWS

Quando você cria uma instância [[Amazon EC2]], um bucket [[Amazon S3]] ou um banco [[Amazon RDS]], o recurso lógico depende de uma base física distribuída entre instalações, equipamentos, energia, refrigeração e conectividade.

Essa camada física explica por que existem [[Regions (Regiões)]], [[Availability Zones (AZ)]], redundância, isolamento de falhas e decisões de localização.

---

## Cuidados importantes de Interpretação

O usuário da nuvem normalmente não escolhe rack, servidor físico ou circuito elétrico. Mesmo assim, precisa entender que falhas físicas podem acontecer e que a arquitetura deve considerar redundância.

Por isso, conceitos físicos aparecem no estudo para fundamentar alta disponibilidade, disaster recovery e topologia global.

---

## Exemplo Arquitetural

Quando uma instância EC2 é criada, ela depende de servidores físicos, rede, energia, refrigeração e armazenamento. Quando uma região possui múltiplas zonas, a AWS está separando falhas físicas e operacionais para reduzir impacto.

---

## Cuidados importantes

Mesmo que a AWS opere a camada física, o cliente ainda precisa desenhar aplicações resilientes.

Não basta confiar no data center. É necessário usar múltiplas zonas, backups, failover e monitoramento conforme a criticidade da aplicação.

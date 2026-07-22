Data Centers são instalações físicas que abrigam servidores, armazenamento, redes, energia e refrigeração. Eles sustentam serviços como [[Amazon EC2]], [[Amazon S3]] e [[Amazon RDS]].

Um data center é um prédio ou conjunto de instalações físicas. Ele não é a mesma coisa que uma [[Availability Zones (AZ)|Zona de Disponibilidade]] nem uma [[Regions (Regiões)|Região]]. Uma AZ pode conter um ou mais data centers. Uma região contém múltiplas AZs.

---

## Visão geral

Pense em Data Centers como a parte que normalmente fica invisível para quem usa nuvem. Você não administra isso diretamente, mas esse conceito explica por que existem regiões, zonas, redundância e preocupação com disponibilidade.

Não pule esta nota: ela ajuda a lembrar que “nuvem” continua dependendo de infraestrutura real.

---

## Por que Importa para AWS

Quando você cria uma instância [[Amazon EC2]], um bucket [[Amazon S3]] ou um banco [[Amazon RDS]], o recurso lógico depende de uma base física distribuída entre instalações, equipamentos, energia, refrigeração e conectividade.

Essa camada física explica por que existem [[Regions (Regiões)]], [[Availability Zones (AZ)]], redundância, [[Isolamento de Falhas]] e decisões de localização. A aplicação usa recursos lógicos, mas esses recursos continuam apoiados em energia, rede, hardware, armazenamento e segurança física.

---

## Cuidados importantes de Interpretação

O usuário da nuvem normalmente não escolhe rack, servidor físico ou circuito elétrico. Mesmo assim, precisa entender que falhas físicas podem acontecer e que a arquitetura deve considerar redundância.

Por isso, conceitos físicos aparecem no estudo para fundamentar alta disponibilidade, disaster recovery e topologia global.

---

## Exemplo Arquitetural

Quando uma instância EC2 é criada, ela depende de servidores físicos, rede, energia, refrigeração e armazenamento. Quando uma AZ contém mais de um data center, a infraestrutura física pode ter redundância interna. Quando uma região possui múltiplas AZs, a AWS oferece isolamento entre locais para reduzir impacto de falhas físicas e operacionais.

---

## Cuidados importantes

Mesmo que a AWS opere a camada física, o cliente ainda precisa desenhar aplicações resilientes.

Não basta confiar no data center. É necessário usar múltiplas zonas, backups, failover e monitoramento conforme a criticidade da aplicação. A responsabilidade pela infraestrutura física é do provedor; a responsabilidade pelo desenho da carga continua com o cliente.

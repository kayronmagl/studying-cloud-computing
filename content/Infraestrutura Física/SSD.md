SSD é armazenamento de estado sólido, com baixa latência e sem partes móveis. Em nuvem, sustenta volumes, bancos e sistemas que precisam de I/O rápido.

---

## O que é

SSD deve ser entendido como parte da base material que sustenta a nuvem. Mesmo quando o usuário acessa serviços pela internet, existem instalações, energia, refrigeração, servidores, redes e controles físicos operando continuamente.

---

## Por que existe

Quando você cria uma instância [[Amazon EC2]], um [[Buckets S3|bucket]] [[Amazon S3]] ou um banco [[Amazon RDS]], o recurso lógico depende de uma base física distribuída entre instalações, equipamentos, energia, refrigeração e conectividade.

Essa camada física explica por que existem [[Regions (Regiões)]], [[Availability Zones (AZ)]], redundância, isolamento de falhas e decisões de localização.

---

## Como funciona

SSD funciona dentro de uma cadeia física: equipamentos são instalados, alimentados, refrigerados, conectados, monitorados e protegidos. Falhas nessa base explicam por que existem redundância, zonas, regiões e planos de recuperação.

---

## Exemplo prático

Quando uma instância [[Amazon EC2|EC2]] é criada, ela depende de servidores físicos, rede, energia, refrigeração e armazenamento. Quando uma região possui múltiplas zonas, a AWS está separando falhas físicas e operacionais para reduzir impacto.

---

## Diferenças importantes

Compare SSD com recursos lógicos como instâncias, buckets e bancos gerenciados. O recurso lógico é o que o cliente configura; a infraestrutura física é o que torna esse recurso possível.

---

## Cuidados

O usuário da nuvem normalmente não escolhe rack, servidor físico ou circuito elétrico. Mesmo assim, precisa entender que falhas físicas podem acontecer e que a arquitetura deve considerar redundância.

Esses conceitos físicos ajudam a entender alta disponibilidade, recuperação de desastre e topologia global sem esquecer que a nuvem continua dependendo de instalações reais.

Mesmo que a AWS opere a camada física, o cliente ainda precisa desenhar aplicações resilientes.

Não basta confiar no data center. É necessário usar múltiplas zonas, backups, failover e monitoramento conforme a criticidade da aplicação.

---

## Relação com outras notas

**Relação com a nuvem**

Pense em SSD como a parte que normalmente fica invisível para quem usa nuvem. Você não administra isso diretamente, mas esse conceito explica por que existem regiões, zonas, redundância e preocupação com disponibilidade.

- [[Amazon EC2]]
- [[Amazon S3]]
- [[Amazon RDS]]
- [[Regions (Regiões)]]
- [[Availability Zones (AZ)]]

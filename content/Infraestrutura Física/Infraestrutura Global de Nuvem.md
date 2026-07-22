Infraestrutura Global de Nuvem é a base física e lógica formada por [[Data Centers]], [[Regions (Regiões)]], [[Availability Zones (AZ)]], [[Edge Locations]] e redes privadas globais.

Na AWS, essa infraestrutura organiza recursos em camadas geográficas. Uma região é uma área geográfica separada. Dentro dela existem zonas de disponibilidade. Cada zona contém um ou mais data centers, com energia, rede e conectividade planejadas para reduzir o impacto de falhas locais.

---

## Relação com a nuvem

Pense em Infraestrutura Global de Nuvem como a parte que normalmente fica invisível para quem usa nuvem. O cliente não escolhe racks, circuitos elétricos ou prédios específicos, mas precisa entender essa estrutura porque ela influencia latência, disponibilidade, recuperação de desastre, residência de dados e custo.


---

## Por que Importa para AWS

Quando você cria uma instância [[Amazon EC2]], um bucket [[Amazon S3]] ou um banco [[Amazon RDS]], o recurso lógico depende de uma base física distribuída entre instalações, equipamentos, energia, refrigeração e conectividade.

Essa camada física explica por que existem [[Regions (Regiões)]], [[Availability Zones (AZ)]], redundância, [[Isolamento de Falhas]] e decisões de localização. Também explica por que criar recursos em nuvem não garante, sozinho, alta disponibilidade ou tolerância a falhas.

As AZs de uma mesma região são interligadas por redes privadas redundantes, de alta largura de banda e baixa latência. Essa proximidade permite arquiteturas [[Arquitetura Multi-AZ|Multi-AZ]], mas não elimina a necessidade de balanceamento, replicação, health checks, observabilidade e testes de recuperação.

---

## Cuidados importantes de Interpretação

O usuário da nuvem normalmente não escolhe rack, servidor físico ou circuito elétrico. Mesmo assim, precisa entender que falhas físicas podem acontecer e que a arquitetura deve considerar redundância, dados, rede, identidade, capacidade e recuperação.

Esses conceitos físicos ajudam a entender alta disponibilidade, recuperação de desastre e topologia global sem esquecer que a nuvem continua dependendo de instalações reais.

---

## Exemplo

Quando uma instância EC2 é criada, ela depende de servidores físicos, rede, energia, refrigeração e armazenamento. Quando uma região possui múltiplas zonas, a AWS oferece limites de isolamento físico e operacional para reduzir impacto de falhas locais.

Isso não distribui automaticamente todos os componentes da aplicação. O cliente ainda precisa decidir em quais AZs criar subnets, instâncias, bancos, load balancers e mecanismos de recuperação.

---

## Cuidados importantes

Mesmo que a AWS opere a camada física, o cliente ainda precisa desenhar aplicações resilientes.

Não basta confiar no data center. É necessário usar múltiplas zonas, backups, failover, monitoramento, alarmes e testes conforme a criticidade da aplicação. Essa divisão se conecta ao [[Modelo de Responsabilidade Compartilhada]]: a AWS fornece a infraestrutura física e limites de isolamento, enquanto o cliente projeta como sua carga usa esses recursos.

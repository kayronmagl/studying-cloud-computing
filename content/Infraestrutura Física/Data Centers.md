Data centers são instalações físicas preparadas para abrigar servidores, armazenamento, redes, energia, refrigeração e controles de segurança. Eles sustentam serviços como [[Amazon EC2]], [[Amazon S3]] e [[Amazon RDS]], mesmo quando o cliente só enxerga recursos lógicos criados por console, API ou automação.

Esse conceito é importante porque “nuvem” não significa ausência de infraestrutura. Significa que a infraestrutura física é operada pelo provedor, enquanto o cliente consome capacidade por meio de serviços.

## Relação com Região e AZ

Um data center é um prédio ou conjunto de instalações físicas. Ele não é a mesma coisa que uma [[Availability Zones (AZ)|Zona de Disponibilidade]] nem uma [[Regions (Regiões)|Região]].

Uma AZ pode conter um ou mais data centers. Uma região contém múltiplas AZs. Essa separação cria limites físicos e operacionais que ajudam a reduzir o impacto de falhas locais. Se um problema atinge uma instalação ou uma zona, a arquitetura pode usar recursos em outra zona, desde que isso tenha sido planejado.

## Como Sustenta a Nuvem

Quando uma instância EC2 é criada, ela depende de servidores físicos, rede, energia, refrigeração e armazenamento. Quando um objeto é gravado no S3 ou um banco é criado no RDS, também existe infraestrutura física sustentando o serviço.

O cliente normalmente não escolhe rack, servidor físico ou circuito elétrico. Essa abstração é uma parte essencial da nuvem. Mesmo assim, a camada física continua influenciando latência, disponibilidade, residência de dados, recuperação de desastre e custo.

## Responsabilidades

A responsabilidade pela infraestrutura física é do provedor. Isso inclui prédios, energia, refrigeração, segurança física, hardware e parte da rede global.

A responsabilidade pelo desenho da carga continua com o cliente. Não basta confiar no data center. Aplicações críticas precisam considerar múltiplas zonas, backups, [[Failover]], monitoramento, testes de recuperação e dados recuperáveis.

## Exemplo

Uma aplicação pode executar instâncias EC2 em duas AZs. Cada AZ depende de data centers físicos, mas a aplicação enxerga recursos lógicos: subnets, instâncias, volumes, bancos e balanceadores. Se a aplicação estiver toda em uma única AZ, uma falha zonal pode derrubá-la. Se estiver distribuída de forma correta, a falha pode ter impacto menor.

Esse exemplo mostra por que data centers aparecem no estudo de nuvem: eles explicam a base física por trás de [[Infraestrutura Global de Nuvem]], isolamento, redundância e disponibilidade.

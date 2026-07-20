Computação em nuvem é um modelo de fornecimento de recursos de tecnologia pela internet. Servidores, redes, armazenamento, bancos de dados e aplicações podem ser provisionados conforme a necessidade, sem que uma organização precise comprar e administrar diretamente toda a infraestrutura física utilizada.

Em um ambiente tradicional, a empresa precisa adquirir equipamentos, preparar espaço físico, instalar servidores, configurar redes, prever capacidade e manter um datacenter em funcionamento. Na nuvem, parte dessas responsabilidades é transferida para provedores como [[AWS (Amazon Web Services)]], [[Google Cloud]] e [[Microsoft Azure]].

Essa mudança afeta tanto a operação técnica quanto o modelo financeiro. A aquisição antecipada de infraestrutura representa investimento de capital, associado a [[CapEx (Capital Expenditures)]]. O uso de recursos contratados conforme a necessidade aumenta a participação de despesas operacionais, associadas a [[OpEx (Operating Expenses)]], [[Consumo sob Demanda]] e [[Pay-as-you-go]].

A nuvem não elimina servidores, redes ou datacenters. Ela modifica quem administra esses recursos, como eles são provisionados e de que forma seu consumo é cobrado.

---

## Como a Computação em Nuvem Funciona

Uma aplicação continua dependendo dos elementos fundamentais da computação: processamento, memória, armazenamento, rede e dados. A diferença está na forma como esses elementos são obtidos e administrados.

Quando um usuário acessa uma aplicação pela [[Internet Pública]], seu dispositivo envia uma solicitação a um sistema executado em algum servidor. Essa comunicação utiliza fundamentos como [[TCP IP]], [[Redes de Computadores]] e [[APIs]]. O servidor recebe a solicitação, aplica as regras da aplicação, consulta dados quando necessário e devolve uma resposta.

Os dados podem ser organizados em diferentes modelos. Sistemas estruturados frequentemente utilizam [[Bancos de Dados Relacionais]] e propriedades como [[Transações ACID]]. Outras aplicações podem utilizar [[NoSQL]] quando precisam de modelos de dados ou padrões de acesso diferentes. Todos esses recursos pertencem ao campo mais amplo de [[Bancos de Dados]].

A diferença entre nuvem e [[On-Premise]] não está na existência desses componentes, mas na forma como são disponibilizados. Em um ambiente local, a organização controla diretamente os equipamentos. Na nuvem, ela utiliza [[Provedores de Nuvem]] e realiza o [[Provisionamento]] de recursos oferecidos como serviços.

Isso permite criar servidores, redes, volumes de armazenamento e bancos de dados com mais rapidez, ajustando a capacidade conforme a demanda e reduzindo a dependência de aquisições físicas antecipadas.

---

## Infraestrutura Física por Trás da Nuvem

Embora os recursos sejam acessados remotamente, a computação em nuvem depende de infraestrutura física real. Os serviços são executados em [[Data Centers]] que concentram equipamentos de computação, armazenamento, rede, energia, refrigeração e segurança.

A capacidade de processamento é fornecida por servidores físicos, incluindo sistemas [[Bare-metal]], organizados em [[Racks]]. Em alguns ambientes são utilizados [[Blade Servers]], que concentram vários servidores modulares em uma mesma estrutura. O armazenamento pode utilizar tecnologias como [[SSD]] e [[NVMe]], escolhidas conforme requisitos de capacidade, latência e desempenho.

A comunicação dentro e entre datacenters depende de [[Switches de Rede]] e de uma ampla infraestrutura de [[Redes de Telecomunicação]]. Tecnologias como [[Cabos Submarinos]], [[Dark Fiber]], [[DWDM]] e [[EDFA]] permitem transmitir dados por longas distâncias e ampliar a capacidade dos enlaces. O volume de dados transportado por uma conexão está relacionado ao [[Computação em Nuvem/Rede Global/Throughput]].

A continuidade operacional depende de sistemas de energia redundantes. [[UPS (Uninterruptible Power Supplies)]], [[Redundância Elétrica]] e [[Geradores a Diesel]] ajudam a manter os equipamentos em funcionamento quando há falhas no fornecimento principal.

Como servidores produzem calor continuamente, os datacenters utilizam [[Gerenciamento Térmico]] e sistemas de [[HVAC (Heating, Ventilation, and Air Conditioning)]]. A eficiência energética desses ambientes pode ser acompanhada por indicadores como [[PUE (Power Usage Effectiveness)]].

A proteção física e operacional segue princípios de [[Segurança em Camadas]], combinando controles de acesso, vigilância, isolamento de áreas, redundância e procedimentos operacionais.

Na prática, os recursos da AWS são executados em estruturas com [[Racks]], [[Blade Servers]], [[SSD]], [[NVMe]] e [[Switches de Rede]], apoiadas por [[Redundância Elétrica]], [[UPS (Uninterruptible Power Supplies)]], [[Geradores a Diesel]], [[HVAC (Heating, Ventilation, and Air Conditioning)]] e métricas como [[PUE (Power Usage Effectiveness)]].

A nuvem, portanto, não é uma estrutura sem servidores. Ela é um modelo no qual o cliente deixa de administrar diretamente uma parte significativa da infraestrutura física.

---

## Infraestrutura Global da AWS

A AWS distribui sua infraestrutura em diferentes níveis geográficos. Essa organização permite aproximar aplicações dos usuários, reduzir o impacto de falhas e atender requisitos técnicos, legais e financeiros.

Os recursos são executados em datacenters agrupados em [[Availability Zones (AZ)|Zonas de Disponibilidade]]. As zonas são locais fisicamente separados, projetados para reduzir a possibilidade de uma única falha interromper toda a aplicação. Cada [[Regions (Regiões)|região]] da AWS possui pelo menos três zonas de disponibilidade e funciona como uma área geográfica independente.

A escolha da região pode ser influenciada pela distância até os usuários, pela [[Latência]], pelo [[Round Trip Time (RTT)]], pela disponibilidade dos serviços, pela [[Variabilidade de Custos]] e por requisitos de [[Conformidade Legal]], incluindo legislações como [[LGPD]] e [[GDPR]].

Além das regiões, a AWS utiliza [[Edge Locations]] para oferecer determinados serviços mais próximos dos usuários. O [[Amazon CloudFront]], por exemplo, distribui conteúdo por pontos de borda para diminuir o tempo necessário para entregá-lo.

Essa estrutura também sustenta estratégias de [[High Availability]] e [[Disaster Recovery (DR)]]. Uma aplicação pode distribuir seus componentes entre zonas de disponibilidade para reduzir o impacto de falhas isoladas.

Quando um componente deixa de funcionar, mecanismos de [[Failover]] podem transferir o processamento para outro recurso saudável. O [[Isolamento de Falhas]] busca impedir que um problema se espalhe, enquanto o estudo de [[Falhas Correlacionadas]] considera situações em que componentes aparentemente independentes compartilham uma mesma dependência.

Planos de recuperação precisam definir quanto tempo uma aplicação pode permanecer indisponível e quantos dados podem ser perdidos. Esses limites são representados por [[Recovery Time Objective (RTO)]] e [[Recovery Point Objective (RPO)]].

A forma como o estado da aplicação é preservado também influencia a recuperação. Conceitos como [[State (Computação)]] e [[Replicação Síncrona]] ajudam a compreender como dados e sessões podem ser mantidos consistentes diante de falhas.

---

## Rede Global, Borda e Entrega de Conteúdo

O desempenho de uma aplicação não depende apenas da capacidade do servidor. Também depende da distância até o usuário, da qualidade das rotas e da quantidade de componentes atravessados pelos dados.

Uma [[CDNs (Content Delivery Networks)|CDN]] distribui conteúdo por diferentes pontos geográficos. Quando um usuário solicita um arquivo, a CDN procura entregá-lo a partir de um local próximo, evitando que todas as solicitações precisem alcançar diretamente o servidor de origem.

O [[Amazon CloudFront]] utiliza esse modelo para distribuir imagens, vídeos, páginas e arquivos estáticos. As cópias temporárias são mantidas em [[Cache]], e o [[TTL (Time To Live)]] determina por quanto tempo elas podem permanecer válidas antes de uma nova consulta à origem.

O direcionamento das solicitações depende de [[DNS]], [[DNS TTL]] e [[Roteamento de Rede]]. Técnicas de [[Roteamento Inteligente]] podem selecionar caminhos ou destinos com base em localização, disponibilidade ou desempenho.

A execução de processamento próximo ao usuário é associada a [[Edge Computing]]. Essa aproximação pode reduzir latência, diminuir tráfego até a região de origem e melhorar a resposta de aplicações distribuídas. Em arquiteturas mais amplas, princípios de [[Software-Defined Networking (SDN)]] permitem controlar o comportamento da rede por software e políticas.

A borda também participa da proteção das aplicações. Ataques de [[DDoS]] podem ser absorvidos ou filtrados por serviços distribuídos. Um [[WAF (Web Application Firewall)]] analisa solicitações HTTP e HTTPS, enquanto mecanismos de [[Segurança Periférica]] aplicam controles antes que o tráfego alcance os componentes internos.

Por isso, [[Edge Computing]], [[WAF (Web Application Firewall)]] e [[Segurança Periférica]] não são assuntos isolados: eles relacionam desempenho, disponibilidade e proteção na parte mais próxima do usuário.

---

## Interagindo com os Serviços da AWS

A AWS pode ser utilizada por diferentes interfaces, mas todas elas operam sobre as mesmas APIs dos serviços.

O [[AWS Management Console]] é a interface gráfica acessada pelo navegador. A [[AWS CLI]] permite executar comandos pelo terminal e automatizar tarefas. Os [[AWS SDKs]] fornecem bibliotecas para que aplicações interajam com os serviços usando linguagens de programação.

Independentemente da interface escolhida, cada ação passa por autenticação e autorização. O [[AWS Identity and Access Management (IAM)]] define quais identidades podem executar determinadas operações sobre determinados recursos.

Criar uma instância, alterar uma regra de rede, enviar um objeto ao S3 ou consultar um banco de dados são exemplos de operações realizadas por essas interfaces. Em ambientes profissionais, automação, controle de permissões e auditoria tornam essas interações reproduzíveis e seguras.

---

## Principais Serviços da AWS

A AWS não deve ser estudada apenas como uma lista de produtos. Cada serviço existe para resolver um tipo de problema relacionado a computação, armazenamento, dados, redes, segurança, integração ou operação.

O [[Amazon EC2]] fornece capacidade computacional por meio de instâncias virtuais. O [[Amazon S3]] armazena objetos. O [[Amazon RDS]] oferece bancos de dados relacionais gerenciados. O [[Amazon DynamoDB]] atende padrões de acesso NoSQL baseados em chave-valor e documentos. A [[Amazon VPC]] permite criar redes virtuais isoladas.

Outros serviços atendem necessidades mais específicas. O [[AWS Elastic Beanstalk]] simplifica a implantação de aplicações, o [[Amazon EKS]] oferece Kubernetes gerenciado e o [[AWS Marketplace]] disponibiliza software de fornecedores independentes. O [[Amazon Augmented AI]] adiciona revisão humana a fluxos de machine learning, mas deixará de aceitar novos clientes em 30 de julho de 2026.

O ponto central é identificar o problema que precisa ser resolvido e, somente depois, selecionar o serviço adequado.

---

## Computação na AWS

Computação é a área responsável por executar aplicações, processos e workloads.

O [[Amazon EC2]] oferece instâncias virtuais configuráveis. Ao criar uma instância, é necessário escolher uma [[Amazon Machine Image (AMI)]], um tipo de instância, rede, armazenamento, permissões e regras de segurança.

O custo e o comportamento das instâncias variam conforme o modelo de compra. [[Instâncias Spot]] utilizam capacidade ociosa e podem ser interrompidas. [[EC2 Instance Savings Plans]] reduzem custos em troca de um compromisso de gasto por hora. [[Hosts Dedicados do Amazon EC2]] são utilizados quando existe exigência de isolamento físico ou controle sobre a alocação do host.

Nem toda aplicação precisa ser administrada diretamente em máquinas virtuais. O [[AWS Elastic Beanstalk]] simplifica a implantação, o [[Amazon ECS]] e o [[Amazon EKS]] orquestram containers, o [[AWS Fargate]] executa containers sem administração direta de servidores e o [[AWS Lambda]] executa funções em resposta a eventos.

---

## Serviços de Computação sem Servidor

[[Computação sem Servidor (Serverless)]] não significa ausência de servidores. Significa que o cliente não administra diretamente a infraestrutura que executa o código.

Uma das formas mais comuns desse modelo é [[Function as a Service (FaaS)]], na qual pequenas unidades de código são executadas em resposta a eventos. O [[AWS Lambda]] é o principal exemplo na AWS: o código é enviado ao serviço, um evento dispara a execução e a cobrança considera o uso efetivo.

Aplicações serverless costumam combinar funções com outros serviços. O [[Amazon API Gateway]] expõe APIs, o [[Amazon EventBridge]] encaminha eventos, o [[Amazon SQS]] desacopla componentes por filas, o [[Amazon SNS]] distribui notificações e o [[AWS Step Functions]] coordena fluxos de execução.

O comportamento real dessas aplicações depende de conceitos como [[Cold Start]], [[Concorrência Lambda]], [[Event Source Mapping]], [[Idempotência]] e [[Dead Letter Queue (DLQ)]]. Eles ajudam a compreender latência inicial, processamento paralelo, leitura de eventos, repetição segura de operações e tratamento de falhas.

---

## Armazenamento na AWS

Armazenamento na AWS não é uma categoria única. A escolha depende de como os dados serão gravados, acessados, compartilhados e recuperados. A visão geral começa em [[Tipos de Armazenamento da AWS]].

O [[Amazon S3]] oferece armazenamento de objetos para arquivos, imagens, backups, logs e conteúdo estático. O [[Amazon EBS]] fornece armazenamento em bloco, geralmente anexado a uma instância [[Amazon EC2]]. O [[Amazon EFS]] oferece um sistema de arquivos compartilhado para múltiplas instâncias Linux. O [[Amazon EC2 Instance Store]] fornece armazenamento temporário ligado ao host físico da instância.

O S3 possui classes voltadas a diferentes padrões de acesso e retenção. [[S3 Standard]] atende dados acessados com frequência. [[S3 Standard-IA]] reduz o custo de armazenamento para dados menos acessados. [[S3 One Zone-IA]] mantém os objetos em uma única zona de disponibilidade. [[S3 Intelligent-Tiering]] move objetos entre camadas conforme o padrão de acesso. Para arquivamento, existem [[S3 Glacier Flexible Retrieval]] e [[S3 Glacier Deep Archive]].

A cópia de objetos entre destinos ou regiões pode ser implementada com [[S3 Replication]]. O [[AWS Backup]] centraliza políticas de backup para diferentes serviços, enquanto o [[Multipart Upload]] divide objetos grandes em partes para tornar o envio mais eficiente e recuperável.

Quando o padrão de acesso é incerto ou muda ao longo do tempo, [[S3 Intelligent-Tiering]] pode ajustar automaticamente a camada de armazenamento sem exigir movimentação manual dos objetos.

---

## Bancos de Dados da AWS

A AWS oferece diferentes mecanismos de banco de dados porque aplicações armazenam e consultam informações de formas distintas.

O [[Amazon RDS]] fornece bancos relacionais gerenciados. O [[Amazon Aurora]] é um mecanismo relacional compatível com MySQL e PostgreSQL, desenvolvido com arquitetura otimizada para a nuvem. O [[Amazon DynamoDB]] atende aplicações que utilizam modelos chave-valor ou documento e precisam de baixa latência em grande escala.

Também existem bancos especializados. O [[Amazon ElastiCache]] mantém dados em memória para reduzir latência. O [[Amazon DocumentDB]] trabalha com documentos. O [[Amazon Neptune]] representa relações complexas em grafos. O [[Amazon Timestream]] atende dados de séries temporais; sua modalidade LiveAnalytics não aceita novos clientes desde 20 de junho de 2025. O [[Amazon Redshift]] é voltado à análise de grandes volumes de dados em data warehouses.

A escolha deve seguir o modelo de dados e o padrão de acesso. O [[Amazon DynamoDB]] é apropriado para chave-valor e documentos, enquanto o [[Amazon Neptune]] é indicado quando as relações entre os dados são parte central das consultas.

---

## Redes na AWS

[[Redes na AWS]] determinam onde os recursos ficam, quem pode acessá-los e por quais caminhos o tráfego circula.

A [[Amazon VPC]] permite criar uma rede virtual isolada. Dentro dela, os recursos são distribuídos em [[Subnets]], e as [[Route Tables]] determinam para onde o tráfego deve ser encaminhado. Um [[Internet Gateway]] conecta recursos públicos à internet, enquanto um [[NAT Gateway]] permite que recursos privados iniciem conexões externas sem receber conexões diretamente.

O controle de tráfego utiliza camadas diferentes. [[Security Groups]] atuam no nível do recurso, como uma instância EC2, enquanto [[Network ACLs]] aplicam regras no nível da subnet. Por isso, [[Security Groups]] e [[Network ACLs]] devem ser compreendidos como controles complementares.

O endereçamento envolve [[Endereços IP Privados]] e [[Endereços IP Públicos]]. A observabilidade pode ser ampliada com [[VPC Flow Logs]], que registram metadados sobre fluxos de rede.

A integração com ambientes locais pode utilizar [[AWS Direct Connect]], uma conexão privada dedicada entre o datacenter e a AWS. O [[Amazon Route 53]] fornece DNS e mecanismos de roteamento de solicitações. Quando o requisito é uma conexão privada dedicada e previsível, [[AWS Direct Connect]] é a solução associada a esse problema.

---

## Segurança na AWS

[[Segurança na AWS]] começa pelo [[Modelo de Responsabilidade Compartilhada]].

A AWS é responsável pela segurança da nuvem, incluindo datacenters, hardware, rede física e camada de virtualização. O cliente é responsável pela segurança na nuvem, incluindo dados, identidades, permissões, aplicações, configurações e, no caso de instâncias EC2, o sistema operacional.

O [[AWS Identity and Access Management (IAM)]] controla identidades e permissões. [[Roles do IAM]] permitem conceder permissões temporárias a usuários, aplicações e serviços. [[Políticas IAM]] descrevem quais ações são permitidas ou negadas. O [[Princípio do Menor Privilégio]] determina que cada identidade receba apenas o acesso necessário.

A proteção da conta também envolve [[Autenticação Multifator (MFA)]] e cuidados especiais com o [[Usuário Root da Conta AWS]], que possui privilégios amplos e deve ser reservado para operações específicas.

Para auditoria e configuração, existem [[AWS CloudTrail]] e [[AWS Config]]. Para detecção e consolidação de riscos, entram [[Amazon GuardDuty]], [[AWS Security Hub]], [[Amazon Inspector]] e [[Amazon Macie]]. Na proteção de aplicações e borda, são utilizados [[AWS WAF]], [[AWS Shield]] e [[AWS Firewall Manager]].

---

## Escalabilidade e Alta Disponibilidade na AWS

Escalabilidade é a capacidade de aumentar a capacidade de um sistema. Elasticidade é a capacidade de aumentar e reduzir recursos conforme a demanda. Alta disponibilidade é a capacidade de continuar funcionando mesmo quando partes do sistema falham.

A nota [[Escalabilidade]] aprofunda as formas de crescimento de uma arquitetura. Na AWS, o [[Amazon EC2 Auto Scaling]] ajusta a quantidade de instâncias, e as [[Scaling Policies]] definem quando aumentar ou reduzir a capacidade.

O [[Amazon CloudWatch]] coleta métricas, logs e alarmes que podem orientar essas decisões. O [[Elastic Load Balancing]] distribui tráfego entre destinos saudáveis, evitando que uma única instância concentre todas as solicitações.

Uma arquitetura comum combina [[Application Load Balancer]], [[Target Groups]], [[Health Checks]], [[Auto Scaling Groups]] e múltiplas [[Availability Zones (AZ)]]. Os health checks identificam destinos indisponíveis, o balanceador deixa de encaminhar tráfego para eles e o Auto Scaling pode substituir ou adicionar capacidade.

Nesse contexto, [[Elastic Load Balancing]] resolve a distribuição de tráfego, enquanto [[Amazon CloudWatch]] fornece observabilidade e sinais para automação.

---

## AWS Well-Architected Framework

O [[AWS Well-Architected Framework]] fornece princípios para avaliar e melhorar workloads executados na AWS. Seu foco não é indicar um único serviço, mas orientar decisões de arquitetura, operação, segurança, confiabilidade, desempenho, custos e sustentabilidade.

Entre os conceitos relacionados estão [[Eficiência de Desempenho]], [[Design à Prova de Falhas]] e [[Acoplamento Fraco]]. Eficiência de desempenho trata da seleção e do uso adequado dos recursos. Design à prova de falhas pressupõe que componentes podem falhar e que a arquitetura deve continuar operando. Acoplamento fraco reduz dependências diretas entre componentes.

Uma arquitetura com [[Acoplamento Fraco]] permite substituir ou recuperar partes do sistema com menor impacto sobre o restante. A distribuição de componentes entre zonas de disponibilidade é um exemplo de [[Design à Prova de Falhas]], pois reduz a dependência de um único local físico.

---

## AWS Cloud Adoption Framework

O [[AWS Cloud Adoption Framework (AWS CAF)]] orienta organizações na adoção da nuvem. Enquanto o Well-Architected avalia a qualidade de workloads e arquiteturas, o CAF trata da transformação organizacional necessária para utilizar a nuvem de forma sustentável.

Essa transformação envolve estratégia, pessoas, governança, plataforma, segurança e operações. O framework organiza essas capacidades em [[Perspectiva de Negócios do AWS CAF]], [[Perspectiva de Pessoas do AWS CAF]], [[Perspectiva de Governança do AWS CAF]], [[Perspectiva de Plataforma do AWS CAF]], [[Perspectiva de Segurança do AWS CAF]] e [[Perspectiva de Operações do AWS CAF]].

O [[AWS Cloud Adoption Framework (AWS CAF)]] é especialmente relevante quando a organização precisa avaliar prontidão, definir um roteiro de transformação, identificar lacunas de capacidade e alinhar tecnologia aos objetivos do negócio.

---

## Serviços de Mensageria na AWS

[[Mensageria]] permite que componentes troquem informações sem depender de comunicação direta e imediata. Ela é importante para reduzir acoplamento, absorver picos de demanda e aumentar a tolerância a falhas.

Antes de comparar serviços, é necessário distinguir [[Filas de Mensagens]], [[Comunicação Síncrona e Assíncrona]], [[Publish Subscribe (Pub Sub)]] e [[Event Streaming]]. Esses modelos representam formas diferentes de transportar e distribuir informações.

O [[Amazon SQS]] implementa filas. Um componente envia uma mensagem e outro a processa posteriormente. Esse desacoplamento evita que o produtor precise aguardar o consumidor e ajuda a lidar com variações de carga.

O [[Amazon SNS]] utiliza publicação e assinatura, distribuindo uma mensagem para vários assinantes. O [[Amazon EventBridge]] encaminha eventos com base em padrões. O [[Amazon MQ]] oferece brokers compatíveis com tecnologias existentes, incluindo [[RabbitMQ]]. O [[Amazon MSK]] fornece Apache Kafka gerenciado, enquanto o [[Amazon Kinesis Data Streams]] trabalha com fluxos contínuos de dados em tempo real.

Quando componentes distribuídos precisam enviar e receber mensagens de forma desacoplada, o [[Amazon SQS]] é uma das principais opções.

---

## Migração e Transferência de Dados para AWS

Migração envolve mover aplicações, bancos de dados, servidores ou grandes volumes de dados para a AWS.

As [[Estratégias de Migração para a Nuvem]] ajudam a decidir se uma aplicação será mantida, apenas transferida, parcialmente ajustada, substituída ou redesenhada. [[Refatorar]] significa modificar a arquitetura para aproveitar serviços e padrões nativos da nuvem.

Para transferência online, o [[AWS DataSync]] automatiza movimentações de arquivos e o [[AWS Transfer Family]] oferece protocolos gerenciados de transferência. O [[AWS Database Migration Service (DMS)]] auxilia na migração de bancos de dados, enquanto o [[AWS Application Migration Service (MGN)]] replica e migra servidores.

A [[AWS Snow Family]] reuniu dispositivos físicos como [[AWS Snowcone]], [[AWS Snowball]], [[AWS Snowball Edge]] e [[AWS Snowmobile]]. Atualmente, esses produtos não estão disponíveis para novos clientes: Snowcone e Snowmobile foram encerrados, e Snowball Edge ficou restrito a clientes existentes. Novos projetos de transferência física devem avaliar o AWS Data Transfer Terminal ou soluções de parceiros.

---

## Precificação e Suporte da AWS

A AWS não utiliza uma única forma de cobrança. Cada serviço mede consumo de acordo com dimensões próprias, como tempo de execução, capacidade provisionada, armazenamento, quantidade de solicitações ou transferência de dados. O [[Modelo de Precificação da AWS]] organiza esses princípios.

O [[AWS Pricing Calculator]] ajuda a estimar custos antes da implantação. O [[AWS Cost Explorer]] apresenta custos e uso ao longo do tempo. O [[AWS Budgets]] permite definir limites e alertas. O [[AWS Cost and Usage Report (CUR)]] fornece dados detalhados de faturamento, enquanto [[Cost Allocation Tags]] ajudam a associar despesas a projetos, equipes ou ambientes. O [[AWS Cost Anomaly Detection]] identifica variações incomuns.

O [[AWS Trusted Advisor]] analisa o ambiente e apresenta recomendações relacionadas a custo, segurança, desempenho, limites e tolerância a falhas. Os [[Planos do AWS Support]] determinam canais de atendimento, tempos de resposta e níveis de orientação técnica.

A otimização pode combinar [[AWS Savings Plans]], [[Reserved Instances]], [[Spot Instances]] e [[Rightsizing]]. Práticas de [[FinOps]] aproximam engenharia, finanças e negócio. O [[Faturamento Consolidado da AWS]] centraliza cobranças de várias contas, enquanto [[Service Quotas]] e [[AWS Health Dashboard]] ajudam a acompanhar limites e eventos que afetam os serviços.

Para análise histórica, utiliza-se [[AWS Cost Explorer]]. Para controle por limites e alertas, utiliza-se [[AWS Budgets]]. Alarmes de faturamento também podem ser integrados ao [[Amazon CloudWatch]].

---

## Gestão Financeira da Nuvem

[[Gestão Financeira da Nuvem]] é o conjunto de práticas usadas para compreender, controlar, prever e otimizar custos em ambientes de nuvem.

O [[Consumo de Tecnologia de Nuvem]] transforma a compra de infraestrutura em uso contínuo de serviços medidos. O [[Modelo de Consumo da Nuvem]] exige acompanhar como recursos são criados, dimensionados, compartilhados e encerrados. A [[Capacidade Igualada à Demanda]] reduz o excesso de recursos, mas depende de automação e observabilidade.

A [[Governança de Custos na AWS]] estabelece responsabilidades, políticas, limites e critérios para tomada de decisão. Esse trabalho pode ser dividido em atividades de [[Acessar Custos da AWS]], [[Organizar Custos da AWS]], [[Compreender Custos da AWS]], [[Controlar Custos da AWS]] e [[Otimizar Custos da AWS]].

Custo em nuvem não é apenas o preço unitário de um serviço. É o resultado conjunto de uso, escala, arquitetura, região, transferência de dados, modelo de compra, disponibilidade e governança.

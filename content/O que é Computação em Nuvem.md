Antes de falar em AWS, serviços ou siglas, vale começar pelo problema que a computação em nuvem tenta resolver. Todo sistema digital precisa de recursos para funcionar: processamento para executar código, memória para manter informações temporárias, armazenamento para guardar dados, rede para permitir comunicação, bancos de dados para organizar informações e ferramentas de operação para observar, proteger e manter tudo isso funcionando.

Em um ambiente tradicional, esses recursos dependem de uma infraestrutura que precisa existir antes do uso. A organização compra servidores, reserva espaço físico, instala equipamentos, configura redes, planeja energia e refrigeração, contrata manutenção e tenta prever quanta capacidade será necessária. Essa previsão raramente é simples. Se a capacidade comprada for grande demais, parte do investimento fica parada. Se for pequena demais, a aplicação pode ficar lenta, indisponível ou exigir uma expansão urgente, cara e demorada.

A computação em nuvem muda esse ponto de partida. Em vez de possuir diretamente toda a infraestrutura física, a organização passa a consumir capacidade de tecnologia como serviço. Isso não quer dizer que a nuvem seja “sem servidores” ou que os computadores desapareceram. Eles continuam existindo em data centers reais. A diferença é que provedores como [[AWS (Amazon Web Services)]], [[Google Cloud]] e [[Microsoft Azure]] operam essa base física em grande escala e entregam ao cliente recursos lógicos que podem ser solicitados, configurados, medidos e encerrados conforme a necessidade.

Essa mudança altera a forma de adquirir, provisionar, operar e pagar por tecnologia. A compra antecipada de bens duráveis, como servidores e equipamentos de rede, se aproxima de [[CapEx (Capital Expenditures)|despesa de capital]], ou CapEx. O consumo recorrente de serviços durante a operação se aproxima de [[OpEx (Operating Expenses)|despesa operacional]], ou OpEx. Na nuvem, esse consumo pode seguir modelos como [[Consumo sob Demanda]] e [[Pay-as-you-go]], em que a cobrança considera tempo de uso, armazenamento, requisições, transferência de dados, capacidade provisionada ou outras dimensões definidas por cada serviço.

Essa flexibilidade explica muitos [[Benefícios da Computação em Nuvem]], mas é importante não transformar benefício potencial em promessa. A nuvem pode reduzir compra antecipada, acelerar a criação de ambientes, facilitar elasticidade e aproximar aplicações de usuários em diferentes locais. Esses ganhos dependem de arquitetura, governança, automação, segurança, monitoramento e controle de custos. Uma aplicação mal desenhada pode ficar cara, frágil ou difícil de operar mesmo estando em um provedor de nuvem.

Também é errado imaginar que o cliente deixa de ter responsabilidades. A nuvem muda a divisão do trabalho, mas não elimina a necessidade de engenharia. Dados, identidades, permissões, configurações, arquitetura, disponibilidade, monitoramento, backups, custos e, em alguns serviços, sistema operacional e aplicações continuam exigindo decisões técnicas.

---

## Como a Computação em Nuvem Funciona

Uma aplicação em nuvem continua sendo uma aplicação. Ela recebe solicitações, executa regras, consulta dados, grava informações e devolve respostas. O que muda não é a natureza básica da computação, mas o caminho usado para obter e administrar os recursos que sustentam esse funcionamento.

Imagine uma aplicação simples de cadastro. Quando uma pessoa preenche um formulário e envia os dados, o navegador faz uma solicitação para algum sistema. Essa comunicação pode passar pela [[Internet Pública]] ou por uma rede privada, dependendo do desenho da aplicação. O servidor recebe a solicitação, valida as informações, executa regras de negócio, consulta ou grava dados e devolve uma resposta. Por trás desse fluxo existem fundamentos como [[TCP IP]], [[Redes de Computadores]] e [[APIs]], mas o raciocínio principal é direto: a nuvem fornece uma maneira diferente de obter os servidores, redes, bancos e ferramentas que participam desse processo.

Os dados dessa aplicação podem ser organizados de formas diferentes. Um sistema financeiro, por exemplo, costuma precisar de [[Bancos de Dados Relacionais]] e propriedades como [[Transações ACID]], porque consistência e integridade são fundamentais. Uma aplicação com grande volume de eventos, sessões ou catálogos pode usar [[NoSQL]] quando o modelo de dados e o padrão de acesso pedem outra abordagem. Estar na nuvem não resolve automaticamente essa escolha; ela continua dependendo do tipo de informação, das consultas, do volume, da consistência exigida e da forma como a aplicação cresce.

A diferença entre nuvem e [[On-Premise]] aparece quando esses componentes precisam ser disponibilizados. Em um ambiente local, a organização controla diretamente os equipamentos ou a instalação que os abriga. Na nuvem, ela utiliza [[Provedores de Nuvem]] e solicita recursos oferecidos como serviços. Essa diferença aparece nos [[Modelos de Implantação em Nuvem]], que ajudam a separar ambientes baseados em nuvem, ambientes locais e arquiteturas híbridas.

Esse ato de solicitar e preparar um recurso para uso é chamado de [[Provisionamento]]. Em vez de instalar fisicamente um servidor, a equipe pode criar uma instância virtual, uma rede, um volume de armazenamento, uma fila ou um banco de dados por meio de uma interface do provedor. O provedor usa virtualização, automação e abstrações de infraestrutura para transformar capacidade física em recursos lógicos que o cliente consegue configurar.

Em provedores como a AWS, essa interação pode acontecer de várias formas. O [[AWS Management Console]] oferece uma interface visual no navegador, útil para aprender, inspecionar e executar operações pontuais. [[APIs]] permitem que sistemas conversem diretamente com os serviços. A [[AWS CLI]] leva essas operações para o terminal. [[AWS SDKs]] permitem que aplicações interajam com a nuvem usando linguagens de programação. Já a [[Computação em Nuvem/Interação com AWS/Infraestrutura como Código (IaC)|Infraestrutura como Código]] registra a configuração em arquivos, tornando o ambiente mais reproduzível e menos dependente de cliques manuais.

O caminho de rede também depende da arquitetura. Alguns acessos usam a internet pública. Outros usam redes privadas, [[VPC Endpoints]], [[AWS PrivateLink]], VPNs ou conexões dedicadas como [[AWS Direct Connect]]. Isso é importante para corrigir uma ideia comum: usar nuvem não significa colocar tudo aberto na internet. Uma aplicação pode ter uma camada pública para receber usuários e manter bancos, instâncias e serviços internos acessíveis apenas por caminhos privados.

Depois que os recursos são criados, eles precisam ser observados e pagos. Métricas, logs e alarmes ajudam a entender uso, desempenho e falhas. A cobrança acompanha o modelo de consumo: recursos ligados, dados armazenados, tráfego, requisições e serviços gerenciados podem gerar custo mesmo quando a aplicação parece pequena. Por isso, nuvem não é só uma forma rápida de criar infraestrutura; é também uma forma diferente de operar e governar tecnologia.

---

## Infraestrutura Física por Trás da Nuvem

Como a nuvem é acessada remotamente, é comum o iniciante imaginar que ela seja algo puramente abstrato. Não é. A computação em nuvem depende de infraestrutura física real. Os serviços são executados em [[Data Centers]] que concentram equipamentos de computação, armazenamento, rede, energia, refrigeração e segurança.

Um data center é uma instalação física preparada para manter equipamentos funcionando continuamente. Dentro dele existem servidores, racks, equipamentos de rede, sistemas de armazenamento, controles de acesso, energia elétrica, refrigeração e procedimentos de operação. A capacidade de processamento pode vir de servidores físicos, incluindo sistemas bare-metal, organizados em racks. O armazenamento pode usar tecnologias como SSD e NVMe, escolhidas conforme requisitos de capacidade, latência e desempenho.

Esses equipamentos precisam conversar entre si e com outros locais. A comunicação dentro e entre data centers depende de [[Switches de Rede]] e de uma ampla infraestrutura de [[Redes de Telecomunicação]]. Cabos submarinos, fibras ópticas dedicadas e tecnologias de transmissão óptica permitem transportar dados por longas distâncias e ampliar a capacidade dos enlaces. O volume de dados que uma conexão consegue transportar em determinado intervalo está relacionado ao [[Computação em Nuvem/Rede Global/Throughput|throughput]].

Também existe uma camada inteira dedicada a manter essa infraestrutura funcionando. [[UPS (Uninterruptible Power Supplies)]], [[Redundância Elétrica]] e [[Geradores a Diesel]] ajudam a sustentar equipamentos quando há falhas no fornecimento principal de energia. Como servidores produzem calor continuamente, os data centers usam [[Gerenciamento Térmico]] e sistemas de [[HVAC (Heating, Ventilation, and Air Conditioning)]]. Indicadores como [[PUE (Power Usage Effectiveness)]] ajudam a acompanhar eficiência energética.

Essa base física também precisa ser protegida. A [[Segurança em Camadas]] combina controles de acesso, vigilância, isolamento de áreas, redundância e procedimentos operacionais. O cliente normalmente não escolhe rack, cabo, circuito elétrico ou prédio específico, mas precisa entender que esses elementos existem porque eles explicam por que a nuvem fala tanto de regiões, zonas, redundância, latência e recuperação.

A nuvem, portanto, não remove a infraestrutura física. Ela muda quem opera essa base e como o cliente consome sua capacidade.

---

## Infraestrutura Global da AWS

A AWS é um exemplo importante de como um provedor organiza essa infraestrutura física em escala global. A ideia não é estudar AWS como se ela fosse sinônimo de computação em nuvem, mas usá-la como referência concreta para entender como um provedor transforma data centers, redes e automação em serviços consumíveis.

Na AWS, a organização geográfica começa pelas [[Regions (Regiões)|regiões]]. Uma região é uma área geográfica separada. Dentro dela existem múltiplas [[Availability Zones (AZ)|Zonas de Disponibilidade]], também chamadas de AZs. Uma AZ é um domínio de isolamento formado por um ou mais data centers, com energia, rede e conectividade planejadas para reduzir o impacto de falhas locais.

Essa diferença merece atenção porque é uma das primeiras confusões de quem está começando. Data center, AZ e região não são a mesma coisa. O data center é a instalação física. A AZ é um limite de isolamento dentro de uma região. A região é a área geográfica que agrupa várias AZs. A quantidade de AZs varia entre regiões e pode mudar ao longo do tempo; neste ponto do estudo, o importante é entender o papel da separação, não memorizar um número.

Essa separação oferece opções arquiteturais. Uma aplicação pode distribuir componentes entre AZs para reduzir dependência de um único local físico. Pode também usar mais de uma região quando há requisitos de recuperação de desastre, residência de dados, alcance geográfico ou continuidade de negócios. Mas a infraestrutura apenas oferece a possibilidade. A aplicação não se torna automaticamente altamente disponível ou resiliente por estar na AWS.

A escolha da região envolve mais do que proximidade geográfica. Distância até usuários, [[Latência]], tempo de ida e volta das requisições, disponibilidade de serviços, variação de custos e requisitos de [[Conformidade Legal]] podem influenciar a decisão. Em alguns sistemas, a residência dos dados é tão importante quanto desempenho. Em outros, a prioridade é reduzir latência para usuários ou manter uma estratégia de recuperação aceitável.

Além das regiões, a AWS utiliza [[Edge Locations]] para aproximar determinados serviços dos usuários. O [[Amazon CloudFront]], por exemplo, distribui conteúdo por pontos de borda para diminuir o tempo necessário para entregar imagens, vídeos, páginas e arquivos estáticos.

Quando um componente deixa de funcionar, mecanismos de [[Failover]] podem transferir a operação para outro recurso, zona ou região. Essa frase parece simples, mas esconde trabalho técnico. É preciso detectar a falha, ter capacidade no destino, manter dados recuperáveis, ajustar roteamento e testar o processo. O [[Isolamento de Falhas]] busca limitar o impacto de um problema, enquanto o estudo de [[Falhas Correlacionadas]] lembra que componentes aparentemente separados podem compartilhar a mesma dependência.

Por isso, planos de recuperação precisam declarar dois limites: quanto tempo uma aplicação pode ficar indisponível e quantos dados podem ser perdidos sem tornar o negócio inviável. Esses limites são representados por [[Recovery Time Objective (RTO)]] e [[Recovery Point Objective (RPO)]]. A forma como o estado da aplicação é preservado também influencia a recuperação; conceitos como [[State (Computação)]] e [[Replicação Síncrona]] ajudam a entender dados, sessões e consistência diante de falhas.


---

## Rede Global, Borda e Entrega de Conteúdo

Depois de entender regiões e zonas, fica mais fácil perceber outro ponto: desempenho não depende apenas da capacidade do servidor. Uma aplicação pode ter bons servidores e ainda assim responder devagar se o usuário estiver distante, se a rota de rede for ruim ou se cada solicitação precisar atravessar muitos componentes.

É aí que entram redes globais e serviços de borda. Uma [[CDNs (Content Delivery Networks)|CDN]] distribui conteúdo por diferentes pontos geográficos. Quando um usuário solicita um arquivo, a CDN tenta entregá-lo a partir de um local próximo, evitando que todas as solicitações precisem alcançar diretamente o servidor de origem.

O [[Amazon CloudFront]] utiliza esse modelo para distribuir imagens, vídeos, páginas e arquivos estáticos. As cópias temporárias ficam em [[Cache]], e o [[TTL (Time To Live)]] define por quanto tempo elas podem permanecer válidas antes de uma nova consulta à origem. O ganho vem de reduzir distância, aliviar o servidor principal e entregar conteúdo repetido de forma mais eficiente.

O direcionamento das solicitações depende de [[DNS]], tempo de vida dos registros e [[Roteamento de Rede]]. Técnicas de [[Roteamento Inteligente]] podem selecionar caminhos ou destinos com base em localização, disponibilidade ou desempenho.

A execução de processamento próximo ao usuário é associada a [[Edge Computing]]. Essa aproximação pode reduzir latência, diminuir tráfego até a região de origem e melhorar a resposta de aplicações distribuídas. Em arquiteturas mais amplas, princípios de [[Software-Defined Networking (SDN)]] permitem controlar o comportamento da rede por software e políticas.

A borda também pode participar da proteção. Ataques de [[DDoS]] podem ser absorvidos ou filtrados por serviços distribuídos. Um [[WAF (Web Application Firewall)]] analisa solicitações HTTP e HTTPS, enquanto mecanismos de [[Segurança Periférica]] aplicam controles antes que o tráfego alcance os componentes internos.

Por isso, borda não é apenas um assunto de velocidade. Ela conecta desempenho, disponibilidade e proteção na parte mais próxima do usuário.

---

## Interagindo com os Serviços da AWS

A AWS pode ser usada por diferentes interfaces. Para quem está começando, o console web costuma ser o primeiro contato. Ele mostra recursos, botões, formulários e telas de configuração. Isso ajuda a enxergar o ambiente, mas não significa que a nuvem seja administrada apenas pelo navegador.

Por trás dessas interfaces estão as APIs dos serviços. O [[AWS Management Console]] chama essas APIs quando o usuário clica e confirma uma ação. A [[AWS CLI]] permite executar operações pelo terminal. Os [[AWS SDKs]] fornecem bibliotecas para que aplicações conversem com os serviços usando linguagens de programação. Em ambientes profissionais, [[Computação em Nuvem/Interação com AWS/Infraestrutura como Código (IaC)|Infraestrutura como Código]] costuma ser usada para declarar redes, permissões, bancos, filas e outros recursos de forma reproduzível.

Independentemente da interface escolhida, cada ação passa por autenticação e autorização. O [[AWS Identity and Access Management (IAM)]] define quais identidades podem executar determinadas operações sobre determinados recursos. Criar uma instância, alterar uma regra de rede, enviar um objeto ao S3 ou consultar um banco de dados são exemplos de ações que precisam de permissão.

Automação ajuda muito, mas não é sinônimo de segurança. Uma automação bem desenhada reduz erro manual, padroniza ambientes e facilita auditoria. Uma automação mal escrita pode criar recursos inseguros, expostos ou caros rapidamente.

---

## Principais Serviços da AWS

Uma forma mais saudável de estudar AWS é começar pela necessidade, não pelo nome do serviço. A pergunta inicial não deve ser “qual produto preciso decorar?”, mas “qual problema técnico estou tentando resolver?”.

Se a aplicação precisa executar código continuamente, entramos na área de computação. O [[Amazon EC2]] oferece instâncias virtuais configuráveis para esse tipo de necessidade. Se a aplicação precisa guardar arquivos, imagens, logs ou backups como objetos, o [[Amazon S3]] é um exemplo central de armazenamento de objetos. Se precisa persistir dados estruturados com SQL, o [[Amazon RDS]] oferece bancos relacionais gerenciados. Se o acesso aos dados segue padrões de chave-valor ou documento em grande escala, o [[Amazon DynamoDB]] aparece como alternativa NoSQL. Se a aplicação precisa de isolamento, sub-redes e controle de tráfego, a [[Amazon VPC]] organiza redes virtuais.

Outros serviços aparecem conforme a arquitetura cresce. O [[AWS Elastic Beanstalk]] simplifica implantação de aplicações. O [[Amazon ECS]] e o [[Amazon EKS]] ajudam a executar containers. O [[AWS Lambda]] executa funções disparadas por eventos. O [[Amazon SQS]] desacopla componentes por filas. O [[Amazon CloudWatch]] coleta sinais de operação. Esses exemplos não esgotam a AWS; eles mostram o método de estudo: entender a necessidade, compreender o tipo de serviço e só então aprofundar o produto.

A nota [[AWS (Amazon Web Services)]] aprofunda a AWS como provedora. As notas de serviços devem ser lidas depois, quando o leitor já entende o problema que cada serviço tenta resolver.

---

## Computação na AWS

Computação é a parte da nuvem responsável por executar aplicações, processos e workloads. Sempre que um sistema precisa rodar código, processar uma requisição, executar uma tarefa em segundo plano ou responder a um evento, alguma forma de computação está envolvida.

O [[Amazon EC2]] oferece instâncias virtuais configuráveis. Ao criar uma instância, a equipe escolhe uma [[Amazon Machine Image (AMI)]], um tipo de instância, rede, armazenamento, permissões e regras de segurança. Essa liberdade é útil quando a aplicação precisa de controle sobre sistema operacional, runtime, agentes, pacotes ou configuração.

O custo e o comportamento dessas instâncias variam conforme o modelo de compra. [[Instâncias Spot]] podem reduzir custo ao usar capacidade ociosa, mas podem ser interrompidas. [[EC2 Instance Savings Plans]] reduzem custo em troca de compromisso de uso. [[Hosts Dedicados do Amazon EC2]] são usados quando há exigência de isolamento físico ou controle sobre a alocação do host. Esse ponto mostra que computação em nuvem não é apenas “ligar servidores virtuais”; envolve custo, risco de interrupção, licenciamento, previsibilidade e operação.

Nem toda aplicação precisa ser administrada diretamente em máquinas virtuais. O [[AWS Elastic Beanstalk]] simplifica a implantação. Amazon ECS e Amazon EKS orquestram containers. O [[AWS Fargate]] executa containers sem administração direta de servidores. O [[AWS Lambda]] executa funções em resposta a eventos. Quanto mais gerenciado o serviço, menos camadas físicas e operacionais o cliente administra diretamente, mas código, permissões, dados, configuração e observabilidade continuam relevantes.

---

## Serviços de Computação sem Servidor

[[Computação sem Servidor (Serverless)]] costuma confundir porque o nome parece dizer que não existem servidores. Existem. A diferença é que o cliente não administra diretamente a infraestrutura que executa o código.

Uma das formas mais comuns desse modelo é [[Function as a Service (FaaS)]]. Nela, pequenas unidades de código são executadas em resposta a eventos. No [[AWS Lambda]], por exemplo, o código é enviado ao serviço; depois, um evento dispara a execução. A cobrança considera o uso efetivo, o que combina bem com workloads que não precisam ficar executando o tempo todo.

Aplicações serverless costumam combinar funções com outros serviços. O [[Amazon API Gateway]] expõe APIs. O [[Amazon EventBridge]] encaminha eventos. Amazon SQS desacopla componentes por filas. O [[Amazon SNS]] distribui notificações. O [[AWS Step Functions]] coordena fluxos de execução. O valor desse modelo aparece quando a arquitetura é orientada a eventos e quando a equipe aceita trabalhar com limites, concorrência, retries e observabilidade de execuções curtas.

O comportamento real dessas aplicações depende de conceitos como [[Cold Start]], concorrência, mapeamento de origem de eventos, [[Idempotência]] e [[Dead Letter Queue (DLQ)]]. Eles ajudam a compreender latência inicial, processamento paralelo, leitura de eventos, repetição segura de operações e tratamento de falhas. Serverless reduz operação de infraestrutura, mas não elimina desenho de arquitetura.

---

## Armazenamento na AWS

Armazenamento parece simples até a primeira decisão real: que tipo de dado será guardado, como ele será lido, quem precisa acessá-lo e o que deve acontecer se algo falhar. Por isso, armazenamento na AWS não é uma categoria única. O ponto de partida é [[Tipos de Armazenamento da AWS]], porque armazenamento de objetos, blocos e arquivos resolvem problemas diferentes.

O [[Amazon S3]] oferece armazenamento de objetos para arquivos, imagens, backups, logs e conteúdo estático. Ele é adequado quando a aplicação precisa guardar objetos acessados por chave, e não um disco tradicional anexado a um servidor. O [[Amazon EBS]] fornece armazenamento em bloco, geralmente anexado a uma instância [[Amazon EC2]], e se aproxima mais da ideia de disco persistente usado por uma máquina. O [[Amazon EFS]] oferece um sistema de arquivos compartilhado para múltiplas instâncias Linux. O [[Amazon EC2 Instance Store]] fornece armazenamento temporário ligado ao host físico da instância.

No S3, as classes de armazenamento existem porque nem todo dado é usado da mesma forma. Um arquivo acessado todos os dias pede uma escolha diferente de um backup que talvez só seja recuperado em uma emergência. Classes como S3 Standard, S3 Standard-IA, S3 One Zone-IA, [[S3 Intelligent-Tiering]] e opções de arquivamento têm diferenças de custo, disponibilidade, latência de recuperação e adequação ao uso.

Quando o assunto é proteção e recuperação, entram decisões como replicação, backup e ciclo de vida. A cópia de objetos entre destinos ou regiões pode ser implementada com [[S3 Replication]]. O [[AWS Backup]] centraliza políticas de backup para diferentes serviços. O [[Multipart Upload]] divide objetos grandes em partes para tornar o envio mais eficiente e recuperável. Esses mecanismos mostram que armazenar dados não é apenas escolher onde gravar; também envolve durabilidade, disponibilidade, recuperação, custo e governança.

---

## Bancos de Dados da AWS

Bancos de dados aparecem cedo no estudo de nuvem porque quase toda aplicação precisa lembrar alguma coisa: usuários, pedidos, pagamentos, eventos, documentos, logs, sessões ou métricas. A AWS oferece diferentes mecanismos porque aplicações armazenam e consultam informações de formas distintas.

Quando os dados possuem tabelas, relações e consultas SQL, o [[Amazon RDS]] fornece bancos relacionais gerenciados. O [[Amazon Aurora]] é um mecanismo relacional compatível com MySQL e PostgreSQL, desenvolvido com arquitetura otimizada para a nuvem. Quando o padrão de acesso é mais próximo de chave-valor ou documento, o [[Amazon DynamoDB]] pode atender aplicações que precisam de baixa latência em grande escala.

Também existem bancos especializados. O [[Amazon ElastiCache]] mantém dados em memória para reduzir latência. O Amazon DocumentDB trabalha com documentos. O [[Amazon Neptune]] representa relações complexas em grafos. O Amazon Timestream atende dados de séries temporais. O [[Amazon Redshift]] é voltado à análise de grandes volumes de dados em data warehouses.

O ponto didático aqui é não escolher banco de dados pelo nome mais conhecido. A escolha deve seguir o modelo de dados, o padrão de acesso, a consistência necessária, o volume esperado, a latência aceitável, a operação e o custo.

---

## Redes na AWS

[[Redes na AWS]] determinam onde os recursos ficam, quem pode acessá-los e por quais caminhos o tráfego circula. Para um iniciante, essa é uma das partes mais importantes: uma aplicação em nuvem não é apenas um conjunto de serviços soltos. Ela precisa de limites, rotas e regras de comunicação.

A [[Amazon VPC]] permite criar uma rede virtual isolada. Dentro dela, os recursos são distribuídos em [[Subnets]], e as [[Route Tables]] determinam para onde o tráfego deve ser encaminhado. Um [[Internet Gateway]] conecta recursos públicos à internet. Um [[NAT Gateway]] permite que recursos privados iniciem conexões externas sem receber conexões diretamente.

O controle de tráfego usa camadas diferentes. [[Security Groups]] atuam no nível do recurso, como uma instância EC2. [[Network ACLs]] aplicam regras no nível da subnet. Eles são controles complementares, não peças intercambiáveis. Essa diferença ajuda a evitar a ideia de que “abrir uma porta” é uma decisão simples e isolada.

O endereçamento envolve [[Endereços IP Privados]] e [[Endereços IP Públicos]]. A observabilidade pode ser ampliada com [[VPC Flow Logs]], que registram metadados sobre fluxos de rede.

A integração com ambientes locais pode utilizar [[AWS Direct Connect]], uma conexão privada dedicada entre o datacenter e a AWS. O [[Amazon Route 53]] fornece DNS e mecanismos de roteamento de solicitações. Redes em nuvem não tratam apenas de “ter internet”; elas definem isolamento, caminhos privados, exposição pública, latência, segurança e conectividade híbrida.

---

## Segurança na AWS

[[Segurança na AWS]] começa por uma ideia que parece simples, mas evita muitos erros: usar nuvem não significa entregar toda a segurança ao provedor. A base desse raciocínio é o [[Modelo de Responsabilidade Compartilhada]].

A AWS é responsável pela segurança da nuvem, incluindo data centers, hardware, rede física e camada de virtualização. O cliente é responsável pela segurança na nuvem, incluindo dados, identidades, permissões, aplicações, configurações e, no caso de instâncias EC2, o sistema operacional.

Essa divisão muda conforme o serviço. Em uma instância EC2, o cliente administra mais camadas, como sistema operacional, patches e configuração da aplicação. Em serviços mais gerenciados, parte da operação direta diminui, mas o cliente ainda precisa cuidar de acesso, dados, criptografia, retenção, logs, monitoramento e custos. O provedor operar a infraestrutura não significa que a aplicação esteja automaticamente bem configurada.

O [[AWS Identity and Access Management (IAM)]] controla identidades e permissões. [[Roles do IAM]] permitem conceder permissões temporárias a usuários, aplicações e serviços. [[Políticas IAM]] descrevem quais ações são permitidas ou negadas. O [[Princípio do Menor Privilégio]] orienta que cada identidade receba apenas o acesso necessário. Esse princípio é simples de explicar e difícil de aplicar bem: permissões amplas facilitam testes rápidos, mas aumentam o impacto de erro, vazamento ou abuso.

A proteção da conta também envolve [[Autenticação Multifator (MFA)]] e cuidados especiais com o [[Usuário Root da Conta AWS]], que possui privilégios amplos e deve ser reservado para operações específicas.

Para auditoria e configuração, existem [[AWS CloudTrail]] e [[AWS Config]]. Para detecção e consolidação de riscos, entram Amazon GuardDuty, AWS Security Hub, Amazon Inspector e Amazon Macie. Na proteção de aplicações e borda, são utilizados [[AWS WAF]], AWS Shield e AWS Firewall Manager.

---

## Escalabilidade e Alta Disponibilidade na AWS

Depois que uma aplicação está no ar, duas perguntas aparecem naturalmente. A primeira é: o que acontece quando mais pessoas começam a usar o sistema? A segunda é: o que acontece quando alguma parte falha? Essas perguntas levam a escalabilidade, elasticidade, alta disponibilidade, tolerância a falhas e failover.

Escalabilidade é a capacidade de um sistema aumentar ou reduzir sua capacidade para lidar com mudanças de demanda. Ela pode ser vertical, quando um recurso recebe mais CPU, memória ou I/O, ou horizontal, quando mais recursos são adicionados ao conjunto. Elasticidade é mais específica: é a capacidade de ajustar recursos dinamicamente conforme a demanda sobe ou desce.

Esses conceitos são próximos, mas não são sinônimos. Um sistema pode ser escalável porque permite adicionar mais servidores manualmente, mas não ser elástico porque não ajusta a capacidade de forma dinâmica. Também é possível aumentar recursos e ainda assim não resolver o problema, se o gargalo estiver no banco de dados, na rede, no código ou em uma dependência externa.

Alta disponibilidade trata de manter um serviço acessível e reduzir tempo de indisponibilidade quando componentes falham. Tolerância a falhas é mais exigente: busca manter a operação durante falhas específicas previstas no projeto, com impacto mínimo ou imperceptível. Nenhuma das duas é consequência automática de usar AWS. Elas dependem de distribuição de recursos, dados recuperáveis, rede bem desenhada, monitoramento, capacidade no destino e testes.

Na AWS, o [[Amazon EC2 Auto Scaling]] pode ajustar a quantidade de instâncias, e as [[Scaling Policies]] definem quando aumentar ou reduzir capacidade. O [[Amazon CloudWatch]] coleta métricas, logs e alarmes que orientam decisões de operação. O [[Elastic Load Balancing]] distribui tráfego entre destinos saudáveis, evitando que uma única instância concentre todas as solicitações.

Um exemplo ajuda. Uma aplicação web pode usar um [[Application Load Balancer]] recebendo tráfego, instâncias em mais de uma AZ, [[Health Checks]] para identificar destinos ruins e [[Auto Scaling Groups]] para ajustar capacidade. Se uma instância falha, o balanceador pode parar de enviar tráfego para ela depois que o health check detectar o problema. O Auto Scaling pode criar outra instância. Isso melhora a disponibilidade, mas não significa funcionamento perfeito.

Pode haver tempo de detecção, reconexões, perda de sessão, degradação temporária e operações repetidas. [[Failover]] também não acontece sozinho: ele depende de detecção, roteamento, capacidade no destino, dados recuperáveis e testes. Para aprofundar a progressão, leia [[Escalabilidade]], [[Elasticidade]], [[Alta Disponibilidade]], [[Tolerância a Falhas]], [[Arquitetura Multi-AZ]] e [[Arquitetura Multi-Region]].

---

## AWS Well-Architected Framework

Quando a aplicação deixa de ser um experimento e passa a sustentar um serviço real, a pergunta muda. Não basta saber qual serviço existe. É preciso avaliar se a arquitetura é operável, segura, confiável, eficiente, financeiramente controlada e sustentável ao longo do tempo.

O [[AWS Well-Architected Framework]] fornece princípios para avaliar e melhorar workloads executados na AWS. Seu foco não é indicar um único serviço, mas orientar decisões de arquitetura, operação, segurança, confiabilidade, desempenho, custos e sustentabilidade.

Entre os conceitos relacionados estão [[Eficiência de Desempenho]], [[Design à Prova de Falhas]] e [[Acoplamento Fraco]]. Eficiência de desempenho trata da seleção e do uso adequado dos recursos. Design à prova de falhas parte da ideia de que componentes podem falhar e de que a arquitetura deve reduzir o impacto dessas falhas. Acoplamento fraco reduz dependências diretas entre componentes.

Uma arquitetura com [[Acoplamento Fraco]] permite substituir ou recuperar partes do sistema com menor impacto sobre o restante. A distribuição de componentes entre zonas de disponibilidade é um exemplo de decisão alinhada a resiliência, pois reduz a dependência de um único local físico. Ainda assim, a qualidade final depende de dados, rede, permissões, observabilidade, capacidade e testes.

---

## AWS Cloud Adoption Framework

O [[AWS Cloud Adoption Framework (AWS CAF)]] olha para outro nível do problema. Enquanto o Well-Architected avalia workloads e arquiteturas, o CAF trata da transformação organizacional necessária para utilizar a nuvem de forma sustentável.

Essa transformação envolve estratégia, pessoas, governança, plataforma, segurança e operações. O framework organiza essas capacidades em perspectivas de negócios, pessoas, governança, plataforma, segurança e operações.

Ele é especialmente relevante quando a organização precisa avaliar prontidão, definir um roteiro de transformação, identificar lacunas de capacidade e alinhar tecnologia aos objetivos do negócio. Isso ajuda a lembrar que adoção de nuvem não é apenas criar recursos técnicos; envolve responsabilidades, processos, pessoas e governança.

---

## Serviços de Mensageria na AWS

À medida que uma aplicação cresce, nem todos os componentes devem depender de comunicação direta e imediata. Se um pedido precisa ser processado, uma confirmação precisa ser enviada ou um evento precisa disparar várias ações, pode ser melhor colocar uma mensagem no meio do fluxo. [[Mensageria]] permite que componentes troquem informações sem ficarem acoplados no mesmo instante.

Antes de comparar serviços, é necessário distinguir [[Filas de Mensagens]], [[Comunicação Síncrona e Assíncrona]], [[Publish Subscribe (Pub Sub)]] e [[Event Streaming]]. Esses modelos representam formas diferentes de transportar e distribuir informações.

O [[Amazon SQS]] implementa filas. Um componente envia uma mensagem e outro a processa posteriormente. Esse desacoplamento evita que o produtor precise aguardar o consumidor e ajuda a lidar com variações de carga. Em vez de perder trabalho durante um pico, a aplicação pode acumular mensagens e processá-las conforme houver capacidade.

O [[Amazon SNS]] utiliza publicação e assinatura, distribuindo uma mensagem para vários assinantes. O [[Amazon EventBridge]] encaminha eventos com base em padrões. O Amazon MQ oferece brokers compatíveis com tecnologias existentes, incluindo RabbitMQ. O Amazon MSK fornece Apache Kafka gerenciado, enquanto o [[Amazon Kinesis Data Streams]] trabalha com fluxos contínuos de dados em tempo real.

Quando componentes distribuídos precisam enviar e receber mensagens de forma desacoplada, o [[Amazon SQS]] é uma das principais opções.

---

## Migração e Transferência de Dados para AWS

Migração envolve mover aplicações, bancos de dados, servidores ou grandes volumes de dados para a AWS. Na prática, migrar raramente significa apenas copiar algo de um lugar para outro. É preciso entender dependências, dados, rede, segurança, janelas de indisponibilidade, custos e o que será mudado ou preservado.

As [[Estratégias de Migração para a Nuvem]] ajudam a decidir se uma aplicação será mantida, apenas transferida, parcialmente ajustada, substituída ou redesenhada. [[Refatorar]] significa modificar a arquitetura para aproveitar serviços e padrões nativos da nuvem, mas nem todo sistema precisa ser refatorado imediatamente. A decisão depende de risco, prazo, custo, dependências e valor técnico.

Para transferência online, o [[AWS DataSync]] automatiza movimentações de arquivos e o [[AWS Transfer Family]] oferece protocolos gerenciados de transferência. O [[AWS Database Migration Service (DMS)]] auxilia na migração de bancos de dados, enquanto o [[AWS Application Migration Service (MGN)]] replica e migra servidores.

Quando a transferência envolve volumes muito grandes, limitações de conectividade ou janelas curtas de migração, a análise pode incluir transferência física de dados e soluções especializadas. Esses detalhes mudam com o tempo e são tratados melhor nas notas específicas de migração e transferência.

---

## Precificação e Suporte da AWS

Custos em nuvem precisam ser estudados desde o começo porque a facilidade de criar recursos também facilita criar gastos. A AWS não utiliza uma única forma de cobrança. Cada serviço mede consumo de acordo com dimensões próprias, como tempo de execução, capacidade provisionada, armazenamento, quantidade de solicitações ou transferência de dados. O [[Modelo de Precificação da AWS]] organiza esses princípios.

Essa cobrança por uso não significa economia garantida. A nuvem pode reduzir compra antecipada e aproximar custo da demanda, mas o resultado depende de arquitetura, tempo de uso, dados armazenados, tráfego, região, contratos, monitoramento, governança e eliminação de desperdício.

Ferramentas como [[AWS Pricing Calculator]], [[AWS Cost Explorer]], [[AWS Budgets]], Cost and Usage Report, tags de alocação de custo e detecção de anomalias ajudam a estimar, acompanhar, distribuir e detectar custos. Elas não substituem decisão de arquitetura: um recurso superdimensionado, uma política de escala sem limite, logs excessivos ou transferência de dados mal planejada continuam gerando gasto.

A otimização pode combinar AWS Savings Plans, Reserved Instances, Spot Instances e [[Rightsizing]]. Práticas de [[FinOps]] aproximam engenharia, finanças e negócio para que custo seja analisado como parte do desenho técnico, não apenas como fatura recebida no fim do mês.

---

## Gestão Financeira da Nuvem

[[Gestão Financeira da Nuvem]] é o conjunto de práticas usadas para compreender, controlar, prever e otimizar custos em ambientes de nuvem. Ela aproxima engenharia, finanças e operação porque o custo nasce de decisões técnicas: onde os recursos ficam, quanto tempo permanecem ligados, como escalam, que dados armazenam e por onde o tráfego passa.

O [[Consumo de Tecnologia de Nuvem]] transforma a compra de infraestrutura em uso contínuo de serviços medidos. O [[Modelo de Consumo da Nuvem]] exige acompanhar como recursos são criados, dimensionados, compartilhados e encerrados. A [[Capacidade Igualada à Demanda]] reduz o excesso de recursos, mas depende de automação, observabilidade e limites.

A [[Governança de Custos na AWS]] estabelece responsabilidades, políticas, limites e critérios para tomada de decisão. Esse trabalho envolve acessar, organizar, compreender, controlar e otimizar custos de forma contínua.

Custo em nuvem não é apenas o preço unitário de um serviço. É o resultado conjunto de uso, escala, arquitetura, região, transferência de dados, modelo de compra, disponibilidade e governança. Por isso, estudar computação em nuvem exige conectar técnica e operação: a mesma decisão que melhora disponibilidade, desempenho ou alcance geográfico também pode alterar custo, complexidade e responsabilidade.

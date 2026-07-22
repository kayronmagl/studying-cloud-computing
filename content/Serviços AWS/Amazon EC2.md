Amazon EC2, ou Amazon Elastic Compute Cloud, é o serviço da [[AWS (Amazon Web Services)]] usado para criar e operar servidores virtuais sob demanda. Esses servidores virtuais são chamados de [[Instância EC2|instâncias EC2]].

O EC2 existe para resolver um problema comum: executar aplicações com controle sobre sistema operacional, capacidade, rede, armazenamento, permissões e software instalado, sem comprar [[Servidores Físicos]] diretamente. Ele é uma forma de consumir computação como serviço, mas ainda preserva bastante responsabilidade operacional para o cliente.

## Como Funciona

Ao criar uma instância EC2, a equipe escolhe uma [[Amazon Machine Image (AMI)]], que define o sistema base da máquina, um [[Tipos de Instância EC2|tipo de instância]], que define CPU, memória e características de desempenho, uma [[Regions (Regiões)|região]], uma [[Availability Zones (AZ)|zona]], uma [[Amazon VPC]], [[Subnets]], [[Security Groups]], forma de acesso, permissões e volumes [[Amazon EBS]].

A AWS traduz essa solicitação em capacidade real dentro da sua [[Infraestrutura Global de Nuvem]]. O cliente não escolhe rack, servidor físico ou circuito elétrico específico, mas escolhe parâmetros suficientes para definir como a instância virtual vai se comportar.

Depois de criada, a instância se comporta como um servidor. Ela pode receber uma aplicação web, um processo interno, um agente de monitoramento, um runtime específico ou um software que exige configuração própria. Essa liberdade é a principal razão para usar EC2 em vez de um serviço mais gerenciado.

## Escalabilidade e Disponibilidade

Uma instância EC2 sozinha é simples de entender, mas também cria risco: se ela falhar, tudo que depende dela pode parar. Para melhorar disponibilidade, EC2 costuma ser combinado com [[Elastic Load Balancing]], [[Auto Scaling Groups]], múltiplas AZs e health checks.

EC2 pode escalar verticalmente, trocando a instância por outra maior, ou horizontalmente, criando várias instâncias para dividir a carga. Escala horizontal pode reduzir [[Single Points of Failure (SPOF)]] e melhorar [[High Availability]], mas isso depende do desenho da aplicação. Se todas as instâncias dependem de um único banco, uma única credencial ou uma única configuração incorreta, o risco continua existindo.

## Exemplo

Uma aplicação web pode usar EC2 para executar o backend, [[Amazon RDS]] para o banco, [[Amazon S3]] para arquivos, [[Amazon CloudFront]] para entrega global e [[Amazon CloudWatch]] para monitoramento. Nesse desenho, EC2 não é a arquitetura inteira. Ele é a camada de computação que executa parte da aplicação.

Se a aplicação crescer, novas instâncias podem ser adicionadas. Se uma instância apresentar falha, o balanceador pode parar de enviar tráfego para ela. Para isso funcionar bem, a aplicação precisa lidar com sessões, logs, configuração, dados e inicialização de instâncias de forma previsível.

## Quando Usar

EC2 é adequado quando a equipe precisa de controle sobre servidor, sistema operacional, runtime, agentes, bibliotecas, rede ou software instalado. Ele também é comum em migrações nas quais uma aplicação existente ainda depende de um ambiente parecido com servidor tradicional.

EC2 pode ser menos adequado quando a equipe quer reduzir ao máximo a administração de sistema operacional, patches, runtime ou capacidade. Nesses casos, serviços como [[AWS Lambda]], [[AWS Fargate]] ou plataformas mais gerenciadas podem ser alternativas, dependendo da aplicação.

## Custos

EC2 não envolve apenas “ligar uma máquina”. O custo depende do tipo de instância, tempo ligada, armazenamento, transferência de dados, snapshots, endereços IP e modelo de compra.

[[Instâncias Spot]] podem reduzir custo ao usar capacidade ociosa, mas podem ser interrompidas. [[EC2 Instance Savings Plans]] reduzem custo em troca de compromisso de uso. Quando há exigência de isolamento físico, licenciamento ou conformidade, [[Hosts Dedicados do Amazon EC2]] podem ser avaliados.

Parar uma instância pode interromper a cobrança de computação, mas volumes EBS, snapshots e alguns recursos associados podem continuar gerando custo. Esse detalhe é importante porque, em nuvem, recurso esquecido também vira despesa.

## Erros Comuns

Um erro comum é tratar EC2 como se fosse apenas um servidor comum hospedado em outro lugar. Ele se parece com um servidor, mas participa de uma arquitetura de nuvem: rede virtual, IAM, imagens, volumes, métricas, automação, balanceamento e modelos de cobrança influenciam seu comportamento.

Outro erro é escolher EC2 quando o problema pede um nível menor de administração. Se a aplicação só precisa executar funções curtas por evento, ou containers sem gerenciar servidores, EC2 pode funcionar, mas talvez não seja a opção operacionalmente mais simples.

Amazon EC2 significa Amazon Elastic Compute Cloud.

É o serviço de computação da [[AWS (Amazon Web Services)]] usado para criar e operar servidores virtuais sob demanda. Esses servidores virtuais são chamados de [[Instância EC2|instâncias EC2]]. O EC2 permite escolher sistema operacional, [[Tipos de Instância EC2|tipo de instância]], rede, armazenamento, permissões e regras de segurança sem comprar [[Servidores Físicos]].

## Como Funciona

Ao criar uma instância, o usuário define uma [[Amazon Machine Image (AMI)]], um tipo de instância, uma [[Regions (Regiões)|região]], uma [[Availability Zones (AZ)|zona]], uma [[Amazon VPC]], [[Subnets]], [[Security Groups]], [[Key Pairs]] e volumes [[Amazon EBS]].

A AWS traduz essa solicitação em capacidade real dentro da sua [[Infraestrutura Global de Nuvem]]. O usuário não escolhe rack nem servidor físico específico.

---

## Escalabilidade

EC2 escala verticalmente, trocando a instância por outra maior, ou horizontalmente, criando várias instâncias atrás de [[Elastic Load Balancing]]. Escala horizontal reduz [[Single Points of Failure (SPOF)]] e melhora [[High Availability]].

---

## Exemplo

Uma aplicação web pode usar EC2 para backend, [[Amazon RDS]] para banco, [[Amazon S3]] para arquivos, [[Amazon CloudFront]] para entrega global e [[Amazon CloudWatch]] para monitoramento. Nesse desenho, EC2 é apenas uma parte de uma arquitetura maior.

## Explicação principal

Amazon EC2 é o serviço de servidores virtuais da AWS.

Ele fornece capacidade computacional configurável: sistema operacional, tipo de instância, rede, armazenamento e permissões.

## Como Funciona na prática

Você escolhe uma AMI, um tipo de instância, uma VPC/subnet, security groups, key pair ou acesso alternativo, volumes e roles IAM.

A instância resultante se comporta como um servidor virtual.

## Quando Usar

Use EC2 quando precisa de controle sobre servidor, sistema operacional, runtime, agentes ou software instalado.

## Diferença para serviços parecidos

* EC2 exige mais administração que Lambda.
* EC2 dá mais controle que Elastic Beanstalk.
* EC2 pode participar de Auto Scaling e Load Balancing.
* EC2 é IaaS: você gerencia mais camadas.

## Cuidado importante

Parar uma instância pode parar cobrança de computação, mas volumes EBS, snapshots e IPs podem continuar cobrando.

---

## Modelos de compra e isolamento físico

Quando você estuda EC2, precisa separar duas perguntas:


* como vou pagar?
* que tipo de isolamento ou capacidade preciso?


Para preço, revise [[EC2 Instance Savings Plans]] e [[Instâncias Spot]].

Para isolamento físico, revise [[Hosts Dedicados do Amazon EC2]].

Isso importa porque EC2 não é só “criar servidor”. Também envolve compromisso financeiro, risco de interrupção e requisitos de licenciamento ou compliance.

---

## Relação com Hosts Dedicados

Quando a exigência é isolamento físico, [[Hosts Dedicados do Amazon EC2]] entram como opção específica dentro do estudo de EC2.

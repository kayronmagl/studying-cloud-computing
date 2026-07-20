Redes na AWS é o conjunto de serviços, conceitos e padrões usados para conectar recursos, isolar ambientes, controlar tráfego, expor aplicações, resolver nomes e integrar a nuvem com redes externas.

Depois de entender computação, armazenamento e bancos, rede se torna inevitável: uma aplicação precisa receber tráfego, acessar banco privado, baixar objetos do S3, chamar APIs, enviar logs e operar com segurança.

---

## Visão geral

Redes na AWS faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Papel da Rede

A rede define:

* onde os recursos ficam;
* quem consegue acessar;
* quais caminhos o tráfego segue;
* quais recursos ficam públicos;
* quais recursos ficam privados;
* como serviços AWS são acessados;
* como ambientes externos se conectam;
* como falhas são isoladas;
* quanto o tráfego pode custar.

Na AWS, o centro dessa arquitetura é a [[Amazon VPC]].

---

## Camadas

A rede pode ser lida em camadas:


* endereçamento: Blocos CIDR, IP privado, IP público.
* segmentação: Subnets, Availability Zones.
* roteamento: Route Tables, Internet Gateway, NAT Gateway.
* segurança: Security Groups, Network ACLs.
* conectividade privada: VPC Endpoints, AWS PrivateLink.
* conectividade entre redes: VPC Peering, Transit Gateway, VPN, Direct Connect.
* entrada de tráfego: Elastic Load Balancing, Route 53, CloudFront.
* observabilidade: VPC Flow Logs, CloudWatch, CloudTrail.


Essa leitura evita tratar rede como uma lista de recursos soltos.

---

## Relação com Outros Eixos

[[Amazon RDS]] normalmente fica em subnets privadas.

[[Amazon EC2]] pode estar em subnet pública ou privada.

[[AWS Lambda]] pode ser configurado para acessar recursos dentro de uma VPC.

[[Amazon S3]] pode ser acessado pela internet pública ou por [[VPC Endpoints]].

[[Amazon CloudFront]] fica na borda, mas normalmente entrega tráfego para origens dentro da AWS.

Por isso, rede é o eixo que amarra computação, armazenamento, bancos, segurança e operação.

---

## Exemplo Prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e VPC Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Cuidados importantes

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

## Como entender isso

Este conceito pertence ao módulo de redes na AWS.

## Ponto central

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

## Como Diferenciar

* VPC é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

## Cuidado importante

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Conceitos que completam o assunto

O [[AWS Client VPN]] conecta usuários remotos à rede, o [[IPv6]] amplia o espaço de endereçamento e o [[Network Address Translation (NAT)]] altera endereços durante o encaminhamento. Eles completam a visão de conectividade sem substituir rotas e controles de acesso.

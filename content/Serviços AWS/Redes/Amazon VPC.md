Amazon VPC significa Amazon Virtual Private Cloud.

É o serviço que permite criar uma rede virtual isolada dentro da AWS. Essa rede se parece conceitualmente com uma rede que uma empresa manteria em um data center próprio, mas é criada por software e integrada aos serviços da nuvem.

---

## Visão geral

Amazon VPC faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Função

Uma VPC define o espaço de rede onde recursos podem existir.

Dentro dela, o usuário configura:

* [[Blocos CIDR]];
* [[Subnets]];
* [[Route Tables]];
* [[Internet Gateway]];
* [[NAT Gateway]];
* [[Security Groups]];
* [[Network ACLs]];
* [[VPC Endpoints]];
* conectividade com outras redes.

A VPC é regional: ela pertence a uma [[Regions (Regiões)|região]], mas suas subnets ficam dentro de [[Availability Zones (AZ)]] específicas.

---

## VPC não é Apenas Isolamento

A VPC também define arquitetura.

Ela separa camadas públicas, privadas e isoladas. Controla rotas. Permite endpoints privados. Conecta redes híbridas. Define onde load balancers, aplicações e bancos serão posicionados.

---

## Exemplo

Uma VPC de produção pode ter:


* 10.0.0.0/16


Dividida em:


* 10.0.1.0/24: subnet pública AZ A.
* 10.0.2.0/24: subnet privada AZ A.
* 10.0.3.0/24: subnet pública AZ B.
* 10.0.4.0/24: subnet privada AZ B.


Esse desenho permite alta disponibilidade e segmentação.

---

## Cuidado

Mudar endereçamento depois pode ser difícil.

Por isso, o planejamento de CIDR deve considerar crescimento, múltiplas VPCs, VPNs, Direct Connect e ausência de sobreposição com redes externas.

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

## Explicação principal

Amazon VPC é a rede virtual isolada onde recursos AWS podem ser colocados.

Ela permite definir blocos CIDR, subnets, rotas, gateways, security groups, NACLs e conectividade.

## Como Funciona

Você cria uma VPC com um intervalo IP, divide em subnets e define rotas.

Subnets públicas têm rota para Internet Gateway. Subnets privadas não recebem acesso direto da internet, mas podem sair via NAT Gateway.

## O que Cai Muito

* VPC é regional.
* Subnet pertence a uma única AZ.
* Security Group é stateful.
* NACL é stateless.
* Route table define caminho do tráfego.
* Internet Gateway permite conectividade pública.
* NAT Gateway permite saída de subnet privada.

## Cuidado importante

Uma subnet não é pública pelo nome. Ela é pública se tiver rota adequada para Internet Gateway e recursos com IP público.

---

## Endereçamento dentro da VPC

Dentro de uma VPC, [[Endereços IP Privados]] identificam recursos na rede interna sem expor esses recursos diretamente à internet.

---

## Observabilidade de rede

[[VPC Flow Logs]] ajudam a investigar tráfego aceito ou rejeitado dentro da VPC.

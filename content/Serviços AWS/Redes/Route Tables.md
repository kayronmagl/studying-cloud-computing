Route Tables são tabelas de roteamento da [[Amazon VPC]].

Elas determinam para onde o tráfego deve ser enviado.

Cada rota possui um destino e um alvo.

Route Tables faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Route Tables deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

Route Tables existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Associação com Subnets**

Subnets são associadas a route tables.

Duas subnets podem ter comportamentos completamente diferentes se estiverem associadas a route tables diferentes.

Isso é o que diferencia, por exemplo, uma subnet pública de uma privada.

**Alvos Comuns**

Rotas podem apontar para:

* [[Internet Gateway]];
* [[NAT Gateway]];
* [[AWS Transit Gateway]];
* [[VPC Peering]];
* [[Gateway VPC Endpoint]];
* virtual private gateway;
* network interface;
* egress-only internet gateway.

---

## Exemplo prático

* Destino: 10.0.0.0/16
* Alvo: local
* Destino: 0.0.0.0/0
* Alvo: Internet Gateway

A rota `local` permite comunicação dentro da [[Amazon VPC|VPC]].

A rota `0.0.0.0/0` representa todo tráfego IPv4 fora das rotas mais específicas.

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Como Diferenciar**

* Subnet pertence a uma única AZ.
* [[Amazon VPC|VPC]] é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

---

## Cuidados

Muitos problemas de conectividade em [[Amazon VPC|VPC]] são problemas de rota.

Se o pacote não sabe para onde ir, não adianta abrir Security Group.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

- [[Amazon VPC]]
- [[Internet Gateway]]
- [[NAT Gateway]]
- [[AWS Transit Gateway]]
- [[VPC Peering]]
- [[Gateway VPC Endpoint]]

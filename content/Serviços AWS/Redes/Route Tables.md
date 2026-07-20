Route Tables são tabelas de roteamento da [[Amazon VPC]].

Elas determinam para onde o tráfego deve ser enviado.

Cada rota possui um destino e um alvo.

---

## Visão geral

Route Tables faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Exemplo

* Destino: 10.0.0.0/16
* Alvo: local
* Destino: 0.0.0.0/0
* Alvo: Internet Gateway


A rota `local` permite comunicação dentro da VPC.

A rota `0.0.0.0/0` representa todo tráfego IPv4 fora das rotas mais específicas.

---

## Associação com Subnets

Subnets são associadas a route tables.

Duas subnets podem ter comportamentos completamente diferentes se estiverem associadas a route tables diferentes.

Isso é o que diferencia, por exemplo, uma subnet pública de uma privada.

---

## Alvos Comuns

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

## Cuidado

Muitos problemas de conectividade em VPC são problemas de rota.

Se o pacote não sabe para onde ir, não adianta abrir Security Group.

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

Este conceito pertence à camada de rede na AWS.

## Ponto central

A VPC define isolamento lógico. Subnets dividem a VPC por zona. Route tables definem caminhos. Gateways conectam a VPC a redes externas ou serviços.

## Como Diferenciar

* Subnet pertence a uma única AZ.
* VPC é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

## Cuidado importante

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

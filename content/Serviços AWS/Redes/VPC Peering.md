VPC Peering conecta duas VPCs diretamente usando endereçamento privado.

Depois de configurado, recursos em uma VPC podem se comunicar com recursos da outra, se rotas e regras de segurança permitirem.


VPC Peering faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Uso

VPC Peering é útil quando duas VPCs precisam conversar diretamente.

Exemplo: uma VPC de aplicação precisa acessar um serviço interno em outra VPC.

---

## Limitações Conceituais

Peering não é transitivo.

Se VPC A está pareada com VPC B, e B está pareada com C, A não conversa automaticamente com C através de B.

---

## Cuidado com CIDR

VPCs com blocos CIDR sobrepostos não podem ser pareadas de forma simples.

Planejamento de endereçamento é fundamental.

---

## Quando Evitar

Em ambientes com muitas VPCs, peering ponto a ponto vira malha difícil de gerenciar.

Nesse caso, [[AWS Transit Gateway]] costuma ser mais adequado.

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

---

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

Egress-Only Internet Gateway permite saída IPv6 de uma VPC para a internet sem permitir conexões iniciadas da internet para dentro.

Ele é parecido conceitualmente com o papel de saída controlada do NAT Gateway, mas aplicado a IPv6.


Egress-Only Internet Gateway faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Por que Existe

No IPv6, endereços podem ser globalmente roteáveis.

Isso muda a forma como se pensa exposição pública.

O egress-only internet gateway permite que recursos iniciem conexões externas, mas bloqueia conexões iniciadas de fora.

---

## Uso

Use quando subnets IPv6 precisam acessar internet, mas os recursos não devem aceitar entrada direta.

---

## Cuidado

Ele não substitui Security Groups, Network ACLs ou desenho correto de rota.

É uma peça de roteamento e controle de direção de tráfego.

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

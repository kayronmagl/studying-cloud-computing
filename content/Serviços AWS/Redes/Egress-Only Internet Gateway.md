Egress-Only Internet Gateway permite saída IPv6 de uma [[Amazon VPC|VPC]] para a internet sem permitir conexões iniciadas da internet para dentro.

Ele é parecido conceitualmente com o papel de saída controlada do NAT Gateway, mas aplicado a IPv6.

Egress-Only Internet Gateway faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Egress-Only Internet Gateway deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

No IPv6, endereços podem ser globalmente roteáveis.

Isso muda a forma como se pensa exposição pública.

O egress-only internet gateway permite que recursos iniciem conexões externas, mas bloqueia conexões iniciadas de fora.

---

## Como funciona

**Uso**

Use quando subnets IPv6 precisam acessar internet, mas os recursos não devem aceitar entrada direta.

---

## Exemplo prático

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

Ele não substitui Security Groups, Network ACLs ou desenho correto de rota.

É uma peça de roteamento e controle de direção de tráfego.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

- [[O que é computação em nuvem]]
- [[Amazon VPC]]
- [[Subnets]]
- [[Route Tables]]

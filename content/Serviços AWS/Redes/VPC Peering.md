[[Amazon VPC|VPC]] Peering conecta duas VPCs diretamente usando endereçamento privado.

Depois de configurado, recursos em uma [[Amazon VPC|VPC]] podem se comunicar com recursos da outra, se rotas e regras de segurança permitirem.

[[Amazon VPC|VPC]] Peering faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

VPC Peering deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

[[Amazon VPC|VPC]] Peering existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Uso**

[[Amazon VPC|VPC]] Peering é útil quando duas VPCs precisam conversar diretamente.

Exemplo: uma [[Amazon VPC|VPC]] de aplicação precisa acessar um serviço interno em outra [[Amazon VPC|VPC]].

**Limitações Conceituais**

Peering não é transitivo.

Se [[Amazon VPC|VPC]] A está pareada com [[Amazon VPC|VPC]] B, e B está pareada com C, A não conversa automaticamente com C através de B.

---

## Exemplo prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Quando Evitar**

Em ambientes com muitas VPCs, peering ponto a ponto vira malha difícil de gerenciar.

Nesse caso, [[AWS Transit Gateway]] costuma ser mais adequado.

**Como Diferenciar**

* Subnet pertence a uma única AZ.
* [[Amazon VPC|VPC]] é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

---

## Cuidados

**Cuidado com CIDR**

VPCs com blocos CIDR sobrepostos não podem ser pareadas de forma simples.

Planejamento de endereçamento é fundamental.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

- [[AWS Transit Gateway]]

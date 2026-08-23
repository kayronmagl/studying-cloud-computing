CIDR significa Classless Inter-Domain Routing.

Um bloco CIDR define um intervalo de endereços IP usando uma notação como:

* 10.0.0.0/16

O número após a barra indica quantos bits representam a parte de rede. Quanto menor o número, maior o intervalo de endereços.

Blocos CIDR faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Blocos CIDR deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

CIDR define crescimento, segmentação e possibilidade de conexão com outras redes.

Se duas redes possuem blocos sobrepostos, conectar essas redes pode ser difícil ou impossível sem tradução, redesenho ou soluções intermediárias.

---

## Como funciona

**Planejamento**

Ao planejar CIDR, considere:

* quantidade de subnets;
* quantidade de zonas;
* crescimento futuro;
* ambientes separados;
* redes on-premise;
* múltiplas contas;
* conectividade híbrida;
* [[Amazon VPC|VPC]] Peering;
* Transit Gateway.

Escolher CIDR pequeno demais limita crescimento. Escolher sem coordenação pode gerar conflito.

---

## Exemplo prático

* 10.0.0.0/16

possui mais endereços que:

* 10.0.1.0/24

Em uma [[Amazon VPC]], o bloco maior costuma ser dividido em [[Subnets]] menores.

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Como Diferenciar**

* [[Amazon VPC|VPC]] é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

---

## Cuidados

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

- [[Amazon VPC]]
- [[Subnets]]

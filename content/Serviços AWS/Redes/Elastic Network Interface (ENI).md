Elastic Network Interface, ou ENI, é uma interface de rede virtual dentro de uma [[Amazon VPC]].

Ela pode ser anexada a instâncias [[Amazon EC2|EC2]] e usada por vários serviços AWS para conectar recursos à rede.

Elastic Network Interface (ENI) faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Elastic Network Interface (ENI) deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

Elastic Network Interface (ENI) existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Componentes**

Uma ENI pode conter:

* endereço IP privado;
* endereços IP privados secundários;
* endereço IPv6;
* [[Elastic IP]] associado;
* [[Security Groups]];
* MAC address;
* descrição;
* origem/destino check.

**Papel**

A ENI é a peça que conecta um recurso à rede.

Sem interface de rede, a instância ou serviço não participa da [[Amazon VPC|VPC]].

**Uso Avançado**

ENIs podem ser movidas em alguns cenários, usadas por appliances, criadas por [[AWS Lambda|Lambda]] em [[Amazon VPC|VPC]], endpoints, load balancers e outros serviços gerenciados.

---

## Exemplo prático

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

Ao conectar [[AWS Lambda]] à [[Amazon VPC|VPC]] ou criar endpoints, ENIs podem aparecer automaticamente. Isso afeta IPs disponíveis, subnets e segurança.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

- [[Amazon VPC]]
- [[Elastic IP]]
- [[Security Groups]]
- [[AWS Lambda]]

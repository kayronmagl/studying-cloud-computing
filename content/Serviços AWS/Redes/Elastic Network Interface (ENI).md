Elastic Network Interface, ou ENI, é uma interface de rede virtual dentro de uma [[Amazon VPC]].

Ela pode ser anexada a instâncias EC2 e usada por vários serviços AWS para conectar recursos à rede.

---

## Visão geral

Elastic Network Interface (ENI) faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Componentes

Uma ENI pode conter:

* endereço IP privado;
* endereços IP privados secundários;
* endereço IPv6;
* [[Elastic IP]] associado;
* [[Security Groups]];
* MAC address;
* descrição;
* origem/destino check.

---

## Papel

A ENI é a peça que conecta um recurso à rede.

Sem interface de rede, a instância ou serviço não participa da VPC.

---

## Uso Avançado

ENIs podem ser movidas em alguns cenários, usadas por appliances, criadas por Lambda em VPC, endpoints, load balancers e outros serviços gerenciados.

---

## Cuidado

Ao conectar [[AWS Lambda]] à VPC ou criar endpoints, ENIs podem aparecer automaticamente. Isso afeta IPs disponíveis, subnets e segurança.

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

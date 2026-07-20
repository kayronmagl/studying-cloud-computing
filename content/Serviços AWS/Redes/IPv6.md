IPv6 é a versão do protocolo IP criada para ampliar o espaço de endereços e modernizar a conectividade da internet.

Na AWS, VPCs e subnets podem usar IPv4, IPv6 ou dual-stack, dependendo da configuração e suporte dos serviços.

---

## Visão geral

IPv6 faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Diferença Geral

IPv4 usa endereços de 32 bits.

IPv6 usa endereços de 128 bits.

Isso amplia drasticamente a quantidade de endereços disponíveis.

---

## Relação com VPC

Ao usar IPv6 em uma [[Amazon VPC]], recursos podem receber endereços IPv6 globalmente roteáveis.

Por isso, o controle de entrada e saída precisa ser pensado com cuidado.

---

## Egress-Only

Para permitir saída IPv6 sem entrada iniciada pela internet, usa-se [[Egress-Only Internet Gateway]].

---

## Cuidado

IPv6 não é “IPv4 com endereço maior”.

Ele muda suposições sobre NAT, exposição e endereçamento público.

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

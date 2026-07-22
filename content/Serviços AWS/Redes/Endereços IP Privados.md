Endereços IP Privados são endereços usados dentro da [[Amazon VPC]] para comunicação interna.

Eles não são roteáveis diretamente pela internet pública.


Endereços IP Privados faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Uso

Recursos em subnets privadas e públicas possuem IP privado.

Mesmo uma instância com IP público normalmente também possui IP privado.

A comunicação interna entre recursos da VPC usa IP privado.

---

## Benefícios

* menor exposição;
* comunicação interna;
* controle por route tables;
* isolamento;
* integração com Security Groups;
* acesso a bancos e serviços privados.

---

## Cuidado

Evite depender de IPs privados fixos quando nomes DNS internos, load balancers ou service discovery forem mais adequados.

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

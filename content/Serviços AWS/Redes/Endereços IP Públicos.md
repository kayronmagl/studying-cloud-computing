Endereços IP Públicos são endereços roteáveis pela internet.

Na AWS, um recurso pode receber IP público automaticamente ou usar um [[Elastic IP]] estático, dependendo da configuração.


Endereços IP Públicos faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Uso

IP público é usado quando um recurso precisa se comunicar diretamente com a internet.

Exemplos:

* bastion host;
* load balancer público;
* instância pública;
* NAT Gateway;
* endpoints públicos.

---

## Cuidado

Ter IP público não significa acesso permitido.

Também é necessário que rotas, Security Groups, Network ACLs e o serviço da máquina permitam tráfego.

---

## Segurança

Quanto menos recursos com IP público direto, menor a superfície de ataque.

Em muitas arquiteturas, apenas load balancers e NAT gateways ficam em subnets públicas.

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

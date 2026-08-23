Elastic IP é um endereço IPv4 público estático alocado à conta AWS.

Ele pode ser associado a recursos como instâncias [[Amazon EC2|EC2]] ou NAT Gateways.

Elastic IP faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Elastic IP deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

IPs públicos automáticos podem mudar quando uma instância é parada e iniciada.

Elastic IP permanece reservado até ser liberado.

Isso é útil quando um endereço fixo é necessário.

---

## Como funciona

**Casos de Uso**

* bastion host;
* NAT Gateway;
* appliances;
* integrações externas que exigem allowlist;
* migração controlada de IP entre recursos.

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

Elastic IP parado ou não associado pode gerar custo.

Além disso, depender de IP fixo para aplicação pública geralmente é menos flexível do que usar [[DNS]], [[Amazon Route 53]] e load balancers.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

- [[DNS]]
- [[Amazon Route 53]]

Registros DNS são entradas que dizem como um nome deve ser resolvido.

Eles ficam dentro de uma [[Hosted Zones|hosted zone]].


Registros DNS faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Tipos Comuns

* A: nome para IPv4.
* AAAA: nome para IPv6.
* CNAME: nome para outro nome.
* MX: e-mail.
* TXT: texto e validações.
* NS: servidores autoritativos.
* Alias: recurso especial do Route 53 para apontar a serviços AWS.

---

## Alias

Alias records do [[Amazon Route 53]] podem apontar para recursos como load balancers, CloudFront e outros destinos AWS.

Eles são úteis porque integram DNS com recursos gerenciados.

---

## TTL

Registros DNS possuem TTL.

TTL define por quanto tempo respostas podem ficar em cache.

---

## Cuidado

TTL alto reduz consultas, mas retarda mudanças.

TTL baixo acelera mudança, mas aumenta consultas e dependência de resolução frequente.

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

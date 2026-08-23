DNS significa Domain Name System.

Ele traduz nomes legíveis em informações de rede, como endereços IP ou aliases de serviços.

Sem DNS, usuários precisariam acessar serviços por endereços técnicos difíceis de memorizar e instáveis.

DNS faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

DNS deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

DNS existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**DNS Interno**

Dentro de uma [[Amazon VPC]], nomes internos também ajudam recursos a se comunicarem sem depender de IPs fixos.

---

## Exemplo prático

* app.exemplo.com: ↓.
* load balancer: ↓.
* aplicação

DNS permite que o nome permaneça estável mesmo quando a infraestrutura muda.

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

DNS possui cache, controlado em parte por [[DNS TTL|TTL]].

Mudanças podem não ser percebidas instantaneamente por todos os clientes, dependendo de TTL e resolvers intermediários.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

**Relação com AWS**

Na AWS, o serviço DNS principal é o [[Amazon Route 53]].

Ele gerencia zonas, registros, roteamento e health checks.

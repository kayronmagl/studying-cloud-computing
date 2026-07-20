DNS significa Domain Name System.

Ele traduz nomes legíveis em informações de rede, como endereços IP ou aliases de serviços.

Sem DNS, usuários precisariam acessar serviços por endereços técnicos difíceis de memorizar e instáveis.

---

## Visão geral

DNS faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Exemplo

* app.exemplo.com: ↓.
* load balancer: ↓.
* aplicação


DNS permite que o nome permaneça estável mesmo quando a infraestrutura muda.

---

## Relação com AWS

Na AWS, o serviço DNS principal é o [[Amazon Route 53]].

Ele gerencia zonas, registros, roteamento e health checks.

---

## DNS Interno

Dentro de uma [[Amazon VPC]], nomes internos também ajudam recursos a se comunicarem sem depender de IPs fixos.

---

## Cuidado

DNS possui cache, controlado em parte por [[DNS TTL|TTL]].

Mudanças podem não ser percebidas instantaneamente por todos os clientes, dependendo de TTL e resolvers intermediários.

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

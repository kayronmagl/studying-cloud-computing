Routing Policies do Route 53 definem como o [[Amazon Route 53]] escolhe respostas DNS.

Elas permitem que DNS participe de estratégias de disponibilidade, performance e distribuição geográfica.


Routing Policies do Route 53 faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Políticas Comuns

* simples;
* ponderada;
* latência;
* failover;
* geolocalização;
* geoproximidade;
* multivalue answer.

---

## Weighted Routing

Roteamento ponderado distribui porcentagens de tráfego.

Exemplo:


* 90% versão atual
* 10% versão nova


É útil para migração gradual.

---

## Latency Routing

Roteamento por latência responde com o destino que tende a oferecer menor latência ao usuário.

---

## Failover

Roteamento de failover usa [[Health Checks]] para responder com destino secundário se o principal falhar.

---

## Cuidado

DNS trabalha com cache.

Mesmo com política sofisticada, clientes e resolvers podem manter respostas por algum tempo.

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

Este conceito pertence à camada de rede na AWS.

## Ponto central

A VPC define isolamento lógico. Subnets dividem a VPC por zona. Route tables definem caminhos. Gateways conectam a VPC a redes externas ou serviços.

## Como Diferenciar

* Subnet pertence a uma única AZ.
* VPC é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

## Cuidado importante

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

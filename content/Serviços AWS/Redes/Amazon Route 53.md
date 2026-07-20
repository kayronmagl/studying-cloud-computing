Amazon Route 53 é o serviço DNS gerenciado da AWS.

Ele permite registrar domínios, hospedar zonas DNS, criar registros, aplicar políticas de roteamento e configurar health checks.

---

## Visão geral

Amazon Route 53 faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Função

Route 53 conecta nomes a destinos.

Exemplos:

* domínio para load balancer;
* domínio para CloudFront;
* subdomínio para API;
* registro interno para serviço privado;
* failover entre destinos.

---

## Hosted Zones

[[Hosted Zones]] armazenam registros DNS de um domínio.

Podem ser públicas ou privadas.

Zonas privadas resolvem nomes apenas dentro de VPCs associadas.

---

## Routing Policies

[[Routing Policies do Route 53]] controlam como respostas DNS são escolhidas.

Exemplos:

* simples;
* ponderada;
* latência;
* failover;
* geolocalização;
* geoproximidade;
* multivalue.

---

## Relação com Load Balancers

Route 53 frequentemente aponta nomes para [[Elastic Load Balancing]] ou [[Amazon CloudFront]].

Assim, usuários acessam nomes estáveis, e a infraestrutura pode mudar por trás.

---

## Cuidado

DNS não substitui load balancer.

DNS resolve nomes. Load balancer distribui tráfego ativo entre destinos.

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

---

## Pontos que Costumam Gerar Confusão

Route 53 permite:

* gerenciar registros DNS para nomes de domínio;
* conectar solicitações de usuários à infraestrutura na AWS e fora da AWS.

---

## Como entender

Route 53 é o serviço DNS da AWS.

Ele traduz nomes como `exemplo.com` para destinos como load balancers, IPs, endpoints ou recursos externos.

---

## Cuidado importante na prática

Route 53 não monitora performance da aplicação como CloudWatch.

Route 53 não automatiza implantação.

Route 53 não fornece relatórios de conformidade como Artifact.

Gateway VPC Endpoint é um tipo de [[VPC Endpoints|VPC Endpoint]] usado para acessar determinados serviços AWS por meio de rotas na VPC.

O exemplo mais comum é acesso privado ao [[Amazon S3]].


Gateway VPC Endpoint faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Como Funciona

O endpoint é associado a route tables.

Quando uma instância em subnet privada acessa S3, a rota direciona o tráfego para o endpoint, não para a internet.

---

## Benefícios

* evita tráfego pela internet pública;
* reduz necessidade de NAT Gateway para esse acesso;
* permite políticas de endpoint;
* melhora controle de segurança.

---

## Cuidado

Gateway endpoint não cria uma ENI dentro da subnet.

Ele funciona como alvo de rota.

Isso diferencia de [[Interface VPC Endpoint]].

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

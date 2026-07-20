NAT Gateway é um serviço de Network Address Translation usado para permitir saída de recursos privados para fora da VPC.

Ele permite que instâncias em [[Subnets Privadas]] iniciem conexões com a internet ou outros serviços, enquanto impede conexões iniciadas de fora diretamente para essas instâncias.

---

## Visão geral

NAT Gateway faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Exemplo

Uma instância privada precisa atualizar pacotes do sistema.

Ela não possui IP público.

O tráfego segue:


* instância privada: ↓.
* route table: ↓.
* NAT Gateway em subnet pública: ↓.
* [[Internet Gateway]]: ↓.
* internet


---

## Alta Disponibilidade

NAT Gateway é zonal.

Em arquiteturas resilientes, é comum criar um NAT Gateway por AZ e configurar subnets privadas para usar o NAT da mesma zona.

Isso evita dependência cruzada entre zonas.

---

## Custo

NAT Gateway pode gerar custo por hora e por volume processado.

Em arquiteturas com muito tráfego para serviços AWS, [[VPC Endpoints]] podem reduzir dependência de NAT.

---

## Cuidado

Não use NAT Gateway para entrada pública.

Ele é para saída iniciada por recursos privados.

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

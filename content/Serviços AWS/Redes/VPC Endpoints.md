VPC Endpoints permitem acessar serviços AWS de dentro de uma [[Amazon VPC]] sem usar a internet pública.

Eles são importantes para segurança, controle de tráfego e redução de dependência de NAT Gateway em alguns cenários.


VPC Endpoints faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Tipos

Existem dois tipos principais:

* [[Gateway VPC Endpoint]];
* [[Interface VPC Endpoint]].

Gateway endpoints são usados para serviços como [[Amazon S3]] e DynamoDB.

Interface endpoints usam [[Elastic Network Interface (ENI)|ENIs]] e são baseados em [[AWS PrivateLink]].

---

## Benefícios

* tráfego privado;
* menor exposição pública;
* controle por políticas;
* acesso sem Internet Gateway;
* redução de tráfego por NAT em alguns casos;
* integração com ambientes privados.

---

## Exemplo

Uma aplicação em subnet privada precisa acessar S3.

Sem endpoint, talvez saia por NAT Gateway.

Com Gateway VPC Endpoint para S3, a rota pode enviar tráfego diretamente para o serviço pela rede AWS, sem internet pública.

---

## Cuidado

Endpoints não substituem IAM.

Mesmo com endpoint privado, permissões de acesso ao serviço continuam necessárias.

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

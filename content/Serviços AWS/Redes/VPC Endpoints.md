[[Amazon VPC|VPC]] Endpoints permitem acessar serviços AWS de dentro de uma [[Amazon VPC]] sem usar a internet pública.

Eles são importantes para segurança, controle de tráfego e redução de dependência de NAT Gateway em alguns cenários.

[[Amazon VPC|VPC]] Endpoints faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

VPC Endpoints deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

* tráfego privado;
* menor exposição pública;
* controle por políticas;
* acesso sem Internet Gateway;
* redução de tráfego por NAT em alguns casos;
* integração com ambientes privados.

---

## Como funciona

**Tipos**

Existem dois tipos principais:

* [[Gateway VPC Endpoint]];
* [[Interface VPC Endpoint]].

Gateway endpoints são usados para serviços como [[Amazon S3]] e [[Amazon DynamoDB|DynamoDB]].

Interface endpoints usam [[Elastic Network Interface (ENI)|ENIs]] e são baseados em [[AWS PrivateLink]].

---

## Exemplo prático

Uma aplicação em subnet privada precisa acessar [[Amazon S3|S3]].

Sem endpoint, talvez saia por NAT Gateway.

Com Gateway [[Amazon VPC|VPC]] Endpoint para [[Amazon S3|S3]], a rota pode enviar tráfego diretamente para o serviço pela rede AWS, sem internet pública.

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Como Diferenciar**

* Subnet pertence a uma única AZ.
* [[Amazon VPC|VPC]] é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

---

## Cuidados

Endpoints não substituem [[AWS Identity and Access Management (IAM)|IAM]].

Mesmo com endpoint privado, permissões de acesso ao serviço continuam necessárias.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

- [[Amazon VPC]]
- [[Gateway VPC Endpoint]]
- [[Interface VPC Endpoint]]
- [[Amazon S3]]
- [[Elastic Network Interface (ENI)]]
- [[AWS PrivateLink]]

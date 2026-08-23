Gateway [[Amazon VPC|VPC]] Endpoint é um tipo de [[VPC Endpoints|VPC Endpoint]] usado para acessar determinados serviços AWS por meio de rotas na [[Amazon VPC|VPC]].

O exemplo mais comum é acesso privado ao [[Amazon S3]].

Gateway [[Amazon VPC|VPC]] Endpoint faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Gateway VPC Endpoint deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

* evita tráfego pela internet pública;
* reduz necessidade de NAT Gateway para esse acesso;
* permite políticas de endpoint;
* melhora controle de segurança.

---

## Como funciona

O endpoint é associado a route tables.

Quando uma instância em subnet privada acessa [[Amazon S3|S3]], a rota direciona o tráfego para o endpoint, não para a internet.

---

## Exemplo prático

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

Gateway endpoint não cria uma ENI dentro da subnet.

Ele funciona como alvo de rota.

Isso diferencia de [[Interface VPC Endpoint]].

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

- [[VPC Endpoints]]
- [[Amazon S3]]
- [[Interface VPC Endpoint]]

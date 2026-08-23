Interface [[Amazon VPC|VPC]] Endpoint é um tipo de [[VPC Endpoints|VPC Endpoint]] baseado em [[AWS PrivateLink]].

Ele cria [[Elastic Network Interface (ENI)|ENIs]] dentro da [[Amazon VPC|VPC]] para permitir acesso privado a serviços.

Interface [[Amazon VPC|VPC]] Endpoint faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Interface VPC Endpoint deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

* acesso privado;
* integração com DNS privado;
* controle por Security Groups;
* menor exposição pública;
* conectividade entre contas e serviços.

---

## Como funciona

A aplicação acessa um endpoint privado dentro da [[Amazon VPC|VPC]].

O tráfego segue pela rede AWS até o serviço, sem precisar sair pela internet pública.

**Uso**

Interface endpoints são usados para muitos serviços AWS e serviços privados expostos por PrivateLink.

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

Interface endpoints têm custo por hora e por dados processados.

Também consomem IPs nas subnets onde são criados.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

- [[VPC Endpoints]]
- [[AWS PrivateLink]]
- [[Elastic Network Interface (ENI)]]

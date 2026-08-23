AWS Transit Gateway é um roteador regional gerenciado que conecta múltiplas VPCs e redes externas.

Ele simplifica arquiteturas que, com peering ponto a ponto, virariam uma malha complexa.

AWS Transit Gateway faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

AWS Transit Gateway deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

* centraliza roteamento;
* reduz malha de peering;
* conecta múltiplas contas;
* integra VPN e Direct Connect;
* melhora governança de rede;
* permite segmentação por route tables.

---

## Como funciona

**Modelo Hub-and-Spoke**

Transit Gateway funciona como hub.

VPCs, VPNs e conexões Direct Connect podem se anexar a ele.

* [[Amazon VPC|VPC]] A: \.
* Transit Gateway: /.
* [[Amazon VPC|VPC]] B

**Uso**

É comum em organizações com várias contas, ambientes, VPCs, regiões e redes on-premise.

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

Transit Gateway adiciona custo e complexidade.

Para duas VPCs simples, [[VPC Peering]] pode ser suficiente. Para dezenas de redes, Transit Gateway tende a ser mais organizado.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

- [[VPC Peering]]

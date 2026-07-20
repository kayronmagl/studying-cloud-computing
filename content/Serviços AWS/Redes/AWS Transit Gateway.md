AWS Transit Gateway é um roteador regional gerenciado que conecta múltiplas VPCs e redes externas.

Ele simplifica arquiteturas que, com peering ponto a ponto, virariam uma malha complexa.

---

## Visão geral

AWS Transit Gateway faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Modelo Hub-and-Spoke

Transit Gateway funciona como hub.

VPCs, VPNs e conexões Direct Connect podem se anexar a ele.


* VPC A: \.
* Transit Gateway: /.
* VPC B


---

## Benefícios

* centraliza roteamento;
* reduz malha de peering;
* conecta múltiplas contas;
* integra VPN e Direct Connect;
* melhora governança de rede;
* permite segmentação por route tables.

---

## Uso

É comum em organizações com várias contas, ambientes, VPCs, regiões e redes on-premise.

---

## Cuidado

Transit Gateway adiciona custo e complexidade.

Para duas VPCs simples, [[VPC Peering]] pode ser suficiente. Para dezenas de redes, Transit Gateway tende a ser mais organizado.

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

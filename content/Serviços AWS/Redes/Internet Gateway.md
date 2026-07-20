Internet Gateway é o componente que permite comunicação entre uma [[Amazon VPC]] e a internet.

Ele funciona como alvo em [[Route Tables]] para tráfego roteável para internet.

---

## Visão geral

Internet Gateway faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Papel

Um Internet Gateway permite:

* saída para internet a partir de recursos públicos;
* entrada da internet para recursos com IP público;
* conectividade de subnets públicas;
* funcionamento de load balancers públicos.

---

## Não Basta Anexar

Anexar um Internet Gateway à VPC não torna tudo público automaticamente.

É necessário ter:

* route table apontando para ele;
* recurso com IP público;
* Security Group permitindo tráfego;
* Network ACL permitindo tráfego;
* serviço escutando na porta.

---

## Relação com Subnets Públicas

Uma subnet pública é pública porque sua route table possui rota para o Internet Gateway.

O nome da subnet não tem efeito técnico.

---

## Cuidado

Evite expor instâncias diretamente quando um load balancer ou CloudFront pode servir como camada de entrada.

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

---

## Acesso pela internet

[[Endereços IP Públicos]] entram quando um recurso precisa se comunicar diretamente com a internet, junto com subnet pública, rota e Internet Gateway.

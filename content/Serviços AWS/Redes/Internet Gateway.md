Internet Gateway é o componente que permite comunicação entre uma [[Amazon VPC]] e a internet.

Ele funciona como alvo em [[Route Tables]] para tráfego roteável para internet.

Internet Gateway faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Internet Gateway deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

Internet Gateway existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Papel**

Um Internet Gateway permite:

* saída para internet a partir de recursos públicos;
* entrada da internet para recursos com IP público;
* conectividade de subnets públicas;
* funcionamento de load balancers públicos.

**Não Basta Anexar**

Anexar um Internet Gateway à [[Amazon VPC|VPC]] não torna tudo público automaticamente.

É necessário ter:

* route table apontando para ele;
* recurso com IP público;
* Security Group permitindo tráfego;
* Network ACL permitindo tráfego;
* serviço escutando na porta.

**Acesso pela internet**

[[Endereços IP Públicos]] entram quando um recurso precisa se comunicar diretamente com a internet, junto com subnet pública, rota e Internet Gateway.

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

Evite expor instâncias diretamente quando um load balancer ou CloudFront pode servir como camada de entrada.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

**Relação com Subnets Públicas**

Uma subnet pública é pública porque sua route table possui rota para o Internet Gateway.

O nome da subnet não tem efeito técnico.

- [[Amazon VPC]]
- [[Route Tables]]
- [[Endereços IP Públicos]]

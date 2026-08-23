Subnets são subdivisões de uma [[Amazon VPC]].

Cada subnet pertence a uma única [[Availability Zones (AZ)|Availability Zone]]. Recursos como instâncias [[Amazon EC2|EC2]], bancos [[Amazon RDS|RDS]], load balancers e interfaces de rede são colocados dentro de subnets.

Subnets faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Subnets deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

Subnets existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Subnet Pública e Privada**

Uma subnet pública é uma subnet cuja route table possui rota para um [[Internet Gateway]].

Uma subnet privada não possui rota direta para Internet Gateway. Ela pode sair para internet por [[NAT Gateway]], mas não recebe conexões iniciadas da internet diretamente.

A diferença é rota, não nome.

**Subnet Isolada**

Uma subnet isolada não possui rota direta para internet nem para NAT.

É útil para bancos, sistemas críticos e recursos que só precisam conversar dentro da [[Amazon VPC|VPC]].

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

Subnets pequenas demais podem ficar sem IP disponível.

Subnets grandes demais podem desperdiçar endereços e dificultar segmentação.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

**Relação com AZ**

Como subnets pertencem a AZs, um desenho resiliente usa subnets equivalentes em múltiplas zonas.

Exemplo:

* AZ A: subnet pública.
* subnet privada: subnet banco.
* AZ B: subnet pública.
* subnet privada: subnet banco.

Isso permite distribuir aplicação e banco entre zonas.

- [[Amazon VPC]]
- [[Availability Zones (AZ)]]
- [[Internet Gateway]]
- [[NAT Gateway]]

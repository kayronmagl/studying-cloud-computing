Subnets são subdivisões de uma [[Amazon VPC]].

Cada subnet pertence a uma única [[Availability Zones (AZ)|Availability Zone]]. Recursos como instâncias EC2, bancos RDS, load balancers e interfaces de rede são colocados dentro de subnets.


Subnets faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Subnet Pública e Privada

Uma subnet pública é uma subnet cuja route table possui rota para um [[Internet Gateway]].

Uma subnet privada não possui rota direta para Internet Gateway. Ela pode sair para internet por [[NAT Gateway]], mas não recebe conexões iniciadas da internet diretamente.

A diferença é rota, não nome.

---

## Subnet Isolada

Uma subnet isolada não possui rota direta para internet nem para NAT.

É útil para bancos, sistemas críticos e recursos que só precisam conversar dentro da VPC.

---

## Relação com AZ

Como subnets pertencem a AZs, um desenho resiliente usa subnets equivalentes em múltiplas zonas.

Exemplo:


* AZ A: subnet pública.
* subnet privada: subnet banco.
* AZ B: subnet pública.
* subnet privada: subnet banco.


Isso permite distribuir aplicação e banco entre zonas.

---

## Cuidado

Subnets pequenas demais podem ficar sem IP disponível.

Subnets grandes demais podem desperdiçar endereços e dificultar segmentação.

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

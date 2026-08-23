Subnets Públicas são subnets com rota para um [[Internet Gateway]].

Elas são usadas para recursos que precisam receber tráfego público diretamente ou servir como ponto de entrada para recursos privados.

Subnets Públicas faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Subnets Públicas deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

---

## Por que existe

Subnets Públicas existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Uso Comum**

Subnets públicas costumam conter:

* [[Application Load Balancer]];
* [[Network Load Balancer]];
* [[NAT Gateway]];
* [[Bastion Host]];
* endpoints públicos específicos.

O ideal é evitar colocar bancos e aplicações internas diretamente em subnets públicas.

**Requisitos para Acesso Público**

Uma instância em subnet pública só é realmente acessível pela internet se houver:

* rota para Internet Gateway;
* IP público ou [[Elastic IP]];
* [[Security Groups]] permitindo tráfego;
* [[Network ACLs]] permitindo tráfego;
* sistema operacional ouvindo na porta correta.

Rede pública é combinação de camadas.

---

## Exemplo prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

Não confunda alcance e função. [[Amazon VPC|VPC]] é regional, subnet é zonal, route table define caminho, Security Group protege recurso, Network ACL protege subnet, NAT Gateway permite saída e Internet Gateway permite conectividade com a internet.

---

## Cuidados

Subnets públicas aumentam superfície de ataque.

Elas devem conter apenas componentes que realmente precisam de exposição ou entrada pública.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

---

## Relação com outras notas

- [[Internet Gateway]]
- [[Application Load Balancer]]
- [[Network Load Balancer]]
- [[NAT Gateway]]
- [[Bastion Host]]
- [[Elastic IP]]
- [[Security Groups]]
- [[Network ACLs]]

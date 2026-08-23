Subnets Privadas são subnets sem rota direta para um [[Internet Gateway]].

Recursos nessas subnets não recebem conexões iniciadas diretamente da internet.

Subnets Privadas faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Subnets Privadas deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

---

## Por que existe

Subnets Privadas existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Uso Comum**

Subnets privadas costumam conter:

* aplicações;
* containers;
* funções [[AWS Lambda|Lambda]] conectadas à [[Amazon VPC|VPC]];
* bancos [[Amazon RDS]];
* caches;
* serviços internos;
* workers.

**Saída para Internet**

Recursos privados podem precisar acessar internet para atualizações, [[APIs|APIs]] externas ou downloads.

Nesse caso, usam [[NAT Gateway]].

* instância privada: ↓.
* [[NAT Gateway]]: ↓.
* [[Internet Gateway]]: ↓.
* internet

A conexão é iniciada de dentro para fora.

---

## Exemplo prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

Não confunda alcance e função. [[Amazon VPC|VPC]] é regional, subnet é zonal, route table define caminho, Security Group protege recurso, Network ACL protege subnet, NAT Gateway permite saída e Internet Gateway permite conectividade com a internet.

---

## Cuidados

Privado não significa seguro por si só.

Ainda é necessário configurar [[Security Groups]], [[Network ACLs]], [[AWS Identity and Access Management (IAM)|IAM]], patches, observabilidade e rotas corretas.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

---

## Relação com outras notas

- [[Internet Gateway]]
- [[Amazon RDS]]
- [[NAT Gateway]]
- [[Security Groups]]
- [[Network ACLs]]

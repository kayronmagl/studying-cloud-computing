Subnets Privadas são subnets sem rota direta para um [[Internet Gateway]].

Recursos nessas subnets não recebem conexões iniciadas diretamente da internet.

---

## Visão geral

Subnets Privadas faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Uso Comum

Subnets privadas costumam conter:

* aplicações;
* containers;
* funções Lambda conectadas à VPC;
* bancos [[Amazon RDS]];
* caches;
* serviços internos;
* workers.

---

## Saída para Internet

Recursos privados podem precisar acessar internet para atualizações, APIs externas ou downloads.

Nesse caso, usam [[NAT Gateway]].


* instância privada: ↓.
* [[NAT Gateway]]: ↓.
* [[Internet Gateway]]: ↓.
* internet


A conexão é iniciada de dentro para fora.

---

## Cuidado

Privado não significa seguro por si só.

Ainda é necessário configurar [[Security Groups]], [[Network ACLs]], IAM, patches, observabilidade e rotas corretas.

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

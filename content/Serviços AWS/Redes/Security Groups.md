Security Groups são firewalls virtuais associados a recursos dentro de uma [[Amazon VPC]].

Eles controlam tráfego de entrada e saída de recursos como instâncias [[Amazon EC2|EC2]], load balancers, bancos [[Amazon RDS|RDS]] e interfaces de rede.

Security Groups faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Security Groups deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

Security Group funciona como firewall virtual no nível do recurso.

Ele é stateful: se você permite uma requisição de entrada, a resposta de saída é automaticamente permitida.

---

## Por que existe

Security Groups existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Stateful**

Security Groups são stateful.

Se uma saída é permitida, a resposta é aceita automaticamente. Se uma entrada é permitida, a resposta também é permitida.

Isso simplifica regras em comparação com mecanismos stateless.

**Regras**

Uma regra define:

* protocolo;
* porta;
* origem ou destino;
* IPv4, IPv6, CIDR ou outro Security Group.

Exemplo:

* permitir HTTPS: protocolo TCP.
* porta 443: origem 0.0.0.0/0.

**Security Group como Origem**

Um padrão forte é usar outro Security Group como origem.

Exemplo:

* [[Amazon RDS|RDS]] aceita porta 5432: origem: security group da aplicação.

Assim, o banco não confia em IPs fixos, mas em pertencimento à camada da aplicação.

---

## Exemplo prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Como Diferenciar**

* [[Amazon VPC|VPC]] é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

**Pontos que Costumam Gerar Confusão**

Quando o cenário indica que um componente da [[Amazon VPC|VPC]] controla tráfego de entrada e saída para instâncias [[Amazon EC2|EC2]], a resposta é [[Security Groups]].

**Diferença para NACL**

* Security Group: recurso, stateful.
* Network ACL: subnet, stateless.

---

## Cuidados

Evite liberar `0.0.0.0/0` para portas administrativas como SSH e RDP.

A regra deve refletir necessidade real, não conveniência.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

Subnet não controla tráfego por si só.

Internet Gateway permite conexão com internet.

Route table define caminho.

Security Group controla permissão de tráfego para o recurso.

---

## Relação com outras notas

- [[Amazon VPC]]

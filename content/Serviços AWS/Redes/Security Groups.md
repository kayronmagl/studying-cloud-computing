Security Groups são firewalls virtuais associados a recursos dentro de uma [[Amazon VPC]].

Eles controlam tráfego de entrada e saída de recursos como instâncias EC2, load balancers, bancos RDS e interfaces de rede.

---

## Visão geral

Security Groups faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Stateful

Security Groups são stateful.

Se uma saída é permitida, a resposta é aceita automaticamente. Se uma entrada é permitida, a resposta também é permitida.

Isso simplifica regras em comparação com mecanismos stateless.

---

## Regras

Uma regra define:

* protocolo;
* porta;
* origem ou destino;
* IPv4, IPv6, CIDR ou outro Security Group.

Exemplo:


* permitir HTTPS: protocolo TCP.
* porta 443: origem 0.0.0.0/0.


---

## Security Group como Origem

Um padrão forte é usar outro Security Group como origem.

Exemplo:


* RDS aceita porta 5432: origem: security group da aplicação.


Assim, o banco não confia em IPs fixos, mas em pertencimento à camada da aplicação.

---

## Cuidado

Evite liberar `0.0.0.0/0` para portas administrativas como SSH e RDP.

A regra deve refletir necessidade real, não conveniência.

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

Este conceito pertence ao módulo de redes na AWS.

## Ponto central

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

## Como Diferenciar

* VPC é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

## Cuidado importante

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Pontos que Costumam Gerar Confusão

Quando o cenário indica que um componente da VPC controla tráfego de entrada e saída para instâncias EC2, a resposta é [[Security Groups]].

---

## Como entender

Security Group funciona como firewall virtual no nível do recurso.

Ele é stateful: se você permite uma requisição de entrada, a resposta de saída é automaticamente permitida.

---

## Diferença para NACL

* Security Group: recurso, stateful.
* Network ACL: subnet, stateless.


---

## Cuidado importante na prática

Subnet não controla tráfego por si só.

Internet Gateway permite conexão com internet.

Route table define caminho.

Security Group controla permissão de tráfego para o recurso.

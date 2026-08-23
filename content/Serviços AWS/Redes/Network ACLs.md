Network ACLs, ou NACLs, são listas de controle de acesso aplicadas no nível da subnet dentro de uma [[Amazon VPC]].

Elas permitem ou negam tráfego de entrada e saída.

Network ACLs faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Network ACLs deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

Network ACLs existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Stateless**

NACLs são stateless.

Isso significa que tráfego de resposta precisa ser permitido explicitamente.

Se você permite entrada em uma porta, precisa garantir que a saída de resposta também seja permitida.

**Ordem de Regras**

NACLs avaliam regras por número, da menor para a maior.

A primeira regra compatível decide.

---

## Exemplo prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Diferença para Security Groups**

* Security Group: recurso.
* stateful: permite tráfego.
* Network ACL: subnet.
* stateless: permite e nega tráfego.

Security Groups são mais usados para controle de aplicação.

NACLs funcionam como camada adicional na fronteira da subnet.

**Como Diferenciar**

* [[Amazon VPC|VPC]] é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

---

## Cuidados

NACL mal configurada pode bloquear tráfego de forma difícil de diagnosticar, especialmente por causa de portas efêmeras.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

- [[Amazon VPC]]

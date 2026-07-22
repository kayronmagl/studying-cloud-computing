Network ACLs, ou NACLs, são listas de controle de acesso aplicadas no nível da subnet dentro de uma [[Amazon VPC]].

Elas permitem ou negam tráfego de entrada e saída.


Network ACLs faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Stateless

NACLs são stateless.

Isso significa que tráfego de resposta precisa ser permitido explicitamente.

Se você permite entrada em uma porta, precisa garantir que a saída de resposta também seja permitida.

---

## Diferença para Security Groups

* Security Group: recurso.
* stateful: permite tráfego.
* Network ACL: subnet.
* stateless: permite e nega tráfego.


Security Groups são mais usados para controle de aplicação.

NACLs funcionam como camada adicional na fronteira da subnet.

---

## Ordem de Regras

NACLs avaliam regras por número, da menor para a maior.

A primeira regra compatível decide.

---

## Cuidado

NACL mal configurada pode bloquear tráfego de forma difícil de diagnosticar, especialmente por causa de portas efêmeras.

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

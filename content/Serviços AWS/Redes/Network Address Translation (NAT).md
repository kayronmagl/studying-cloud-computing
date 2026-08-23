Network Address Translation, ou NAT, é a técnica de traduzir endereços IP durante a passagem do tráfego por um dispositivo ou serviço de rede.

Na AWS, o caso mais comum é o [[NAT Gateway]], usado para permitir que recursos em subnets privadas acessem a internet sem receber conexões iniciadas externamente.

Network Address Translation (NAT) faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Um recurso privado usa IP interno.

Ao sair para a internet por NAT, o tráfego parece partir do endereço público associado ao NAT.

A resposta volta para o NAT, que encaminha ao recurso interno correto.

Network Address Translation (NAT) deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

Network Address Translation (NAT) existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Uso**

NAT é usado para:

* saída de instâncias privadas;
* atualizações de sistema;
* acesso a [[APIs|APIs]] públicas;
* downloads;
* integrações externas.

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

---

## Cuidados

NAT não é firewall completo.

Ele controla direção de conexão, mas regras de segurança, rotas, [[AWS Identity and Access Management (IAM)|IAM]], logs e monitoramento continuam necessários.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

- [[NAT Gateway]]

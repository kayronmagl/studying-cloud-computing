AWS PrivateLink é a tecnologia que permite acessar serviços de forma privada, usando endpoints dentro da [[Amazon VPC|VPC]].

Ela evita expor serviços pela internet pública e permite conectividade privada entre VPCs, contas e serviços AWS.

AWS PrivateLink faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Em vez de publicar um serviço em um IP público, ele pode ser oferecido por endpoint privado.

Consumidores acessam esse endpoint dentro de suas próprias VPCs.

AWS PrivateLink deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

AWS PrivateLink existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Uso**

PrivateLink é usado para:

* acessar serviços AWS;
* expor serviços internos entre contas;
* vender serviços privados;
* conectar SaaS;
* reduzir exposição pública.

---

## Exemplo prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Diferença para Peering**

[[VPC Peering]] conecta redes em camada IP.

PrivateLink expõe um serviço específico.

Se você quer conectividade ampla entre VPCs, peering ou Transit Gateway pode fazer sentido. Se quer expor apenas um serviço, PrivateLink costuma ser mais controlado.

**Como Diferenciar**

* [[Amazon VPC|VPC]] é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

---

## Cuidados

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

**Relação com Interface Endpoint**

[[Interface VPC Endpoint]] é o recurso usado para consumir serviços via PrivateLink.

Ele cria ENIs na [[Amazon VPC|VPC]] do consumidor.

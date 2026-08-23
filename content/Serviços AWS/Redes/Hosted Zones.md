Hosted Zones são contêineres de registros DNS no [[Amazon Route 53]].

Uma hosted zone corresponde normalmente a um domínio ou subdomínio.

Hosted Zones faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

Hosted Zones deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

Hosted Zones existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Pública**

Hosted zone pública responde consultas vindas da internet.

Exemplo:

* exemplo.com
* api.exemplo.com
* www.exemplo.com

**Privada**

Hosted zone privada responde apenas dentro de VPCs associadas.

É usada para nomes internos.

Exemplo:

* db.interno.local
* api.interno.local

**Registros**

Hosted zones contêm [[Registros DNS]], como A, AAAA, CNAME, MX, TXT e aliases para recursos AWS.

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

Misturar nomes públicos e privados sem estratégia pode causar confusão de resolução.

É comum separar zonas públicas e privadas de forma explícita.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

- [[Amazon Route 53]]
- [[Registros DNS]]

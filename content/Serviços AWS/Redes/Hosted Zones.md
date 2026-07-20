Hosted Zones são contêineres de registros DNS no [[Amazon Route 53]].

Uma hosted zone corresponde normalmente a um domínio ou subdomínio.

---

## Visão geral

Hosted Zones faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Pública

Hosted zone pública responde consultas vindas da internet.

Exemplo:


* exemplo.com
* api.exemplo.com
* www.exemplo.com


---

## Privada

Hosted zone privada responde apenas dentro de VPCs associadas.

É usada para nomes internos.

Exemplo:


* db.interno.local
* api.interno.local


---

## Registros

Hosted zones contêm [[Registros DNS]], como A, AAAA, CNAME, MX, TXT e aliases para recursos AWS.

---

## Cuidado

Misturar nomes públicos e privados sem estratégia pode causar confusão de resolução.

É comum separar zonas públicas e privadas de forma explícita.

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

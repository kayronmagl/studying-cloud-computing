AWS PrivateLink é a tecnologia que permite acessar serviços de forma privada, usando endpoints dentro da VPC.

Ela evita expor serviços pela internet pública e permite conectividade privada entre VPCs, contas e serviços AWS.

---

## Visão geral

AWS PrivateLink faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Ideia

Em vez de publicar um serviço em um IP público, ele pode ser oferecido por endpoint privado.

Consumidores acessam esse endpoint dentro de suas próprias VPCs.

---

## Relação com Interface Endpoint

[[Interface VPC Endpoint]] é o recurso usado para consumir serviços via PrivateLink.

Ele cria ENIs na VPC do consumidor.

---

## Uso

PrivateLink é usado para:

* acessar serviços AWS;
* expor serviços internos entre contas;
* vender serviços privados;
* conectar SaaS;
* reduzir exposição pública.

---

## Diferença para Peering

[[VPC Peering]] conecta redes em camada IP.

PrivateLink expõe um serviço específico.

Se você quer conectividade ampla entre VPCs, peering ou Transit Gateway pode fazer sentido. Se quer expor apenas um serviço, PrivateLink costuma ser mais controlado.

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

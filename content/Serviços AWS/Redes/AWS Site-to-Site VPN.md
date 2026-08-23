AWS Site-to-Site VPN cria túneis VPN IPsec entre uma rede externa e a AWS.

Ela conecta, por exemplo, uma rede on-premise a uma [[Amazon VPC]] ou a um [[AWS Transit Gateway]].

AWS Site-to-Site VPN faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

AWS Site-to-Site VPN deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

---

## Por que existe

AWS Site-to-Site VPN existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**Uso**

* conexão híbrida rápida;
* extensão temporária de rede;
* backup de Direct Connect;
* acesso seguro entre data center e AWS;
* ambientes corporativos.

**Componentes**

Uma arquitetura comum envolve:

* customer gateway;
* virtual private gateway ou transit gateway;
* túneis IPsec;
* roteamento estático ou BGP.

---

## Exemplo prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Diferença para Direct Connect**

[[AWS Direct Connect]] é circuito dedicado.

Site-to-Site VPN usa internet pública com criptografia.

VPN costuma ser mais rápida de implementar. Direct Connect tende a ser mais previsível para tráfego intenso.

**Como Diferenciar**

* [[Amazon VPC|VPC]] é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

---

## Cuidados

VPN depende da qualidade da internet entre as pontas.

Para workloads críticos, use redundância.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Relação com outras notas

- [[Amazon VPC]]
- [[AWS Transit Gateway]]
- [[AWS Direct Connect]]

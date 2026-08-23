[[Amazon VPC|VPC]] Flow Logs registram metadados de tráfego de rede em uma [[Amazon VPC]].

Eles podem ser habilitados em VPCs, subnets ou interfaces de rede.

[[Amazon VPC|VPC]] Flow Logs faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que é

VPC Flow Logs deve ser entendido pelo caminho do tráfego: origem, destino, protocolo, porta, rota, nome DNS e limite de isolamento. Rede na AWS define quem consegue falar com quem e por onde os pacotes passam.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

[[Amazon VPC|VPC]] Flow Logs existe para controlar comunicação entre recursos, usuários, serviços e ambientes externos. Sem desenho de rede claro, surgem exposição indevida, falhas de conectividade, latência difícil de explicar e custo de tráfego inesperado.

---

## Como funciona

**O que Registram**

Flow Logs registram informações como:

* origem;
* destino;
* porta;
* protocolo;
* ação aceita ou rejeitada;
* quantidade de bytes;
* interface;
* janela de tempo.

Eles não registram o conteúdo completo dos pacotes.

**Uso**

* diagnóstico de conectividade;
* auditoria;
* investigação de segurança;
* análise de tráfego;
* identificação de regras bloqueando acesso;
* observação de padrões incomuns.

---

## Exemplo prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e [[Amazon VPC|VPC]] Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Diferenças importantes

**Como Diferenciar**

* Subnet pertence a uma única AZ.
* [[Amazon VPC|VPC]] é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

---

## Cuidados

Flow Logs geram volume de dados.

É preciso planejar retenção, custo e filtros.

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

**Relação com CloudWatch**

Flow Logs podem ser enviados para [[Amazon CloudWatch]], [[Amazon S3|S3]] ou outros destinos compatíveis, dependendo da configuração.

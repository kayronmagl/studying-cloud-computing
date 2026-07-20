VPC Flow Logs registram metadados de tráfego de rede em uma [[Amazon VPC]].

Eles podem ser habilitados em VPCs, subnets ou interfaces de rede.

---

## Visão geral

VPC Flow Logs faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## O que Registram

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

---

## Uso

* diagnóstico de conectividade;
* auditoria;
* investigação de segurança;
* análise de tráfego;
* identificação de regras bloqueando acesso;
* observação de padrões incomuns.

---

## Relação com CloudWatch

Flow Logs podem ser enviados para [[Amazon CloudWatch]], S3 ou outros destinos compatíveis, dependendo da configuração.

---

## Cuidado

Flow Logs geram volume de dados.

É preciso planejar retenção, custo e filtros.

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

Este conceito pertence à camada de rede na AWS.

## Ponto central

A VPC define isolamento lógico. Subnets dividem a VPC por zona. Route tables definem caminhos. Gateways conectam a VPC a redes externas ou serviços.

## Como Diferenciar

* Subnet pertence a uma única AZ.
* VPC é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

## Cuidado importante

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

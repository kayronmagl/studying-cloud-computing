Gateway Load Balancer, ou GWLB, é um tipo de load balancer usado para implantar e escalar appliances virtuais de rede.

Ele é comum em arquiteturas com firewalls, IDS/IPS, inspeção de tráfego e appliances de segurança.

---

## Visão geral

Gateway Load Balancer ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Papel

GWLB combina balanceamento de carga com ponto de inserção transparente para appliances.

---

## Uso

* firewalls virtuais;
* inspeção de pacotes;
* appliances de segurança;
* tráfego centralizado;
* arquiteturas de segurança em múltiplas VPCs.

---

## Diferença

[[Application Load Balancer]] é para HTTP/HTTPS.

[[Network Load Balancer]] é para camada de transporte.

Gateway Load Balancer é para appliances de rede.

---

## Cuidado

GWLB é avançado.

Ele deve ser usado quando há necessidade real de inspeção ou appliance de rede escalável.

---

## Exemplo Prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Cuidados importantes

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

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

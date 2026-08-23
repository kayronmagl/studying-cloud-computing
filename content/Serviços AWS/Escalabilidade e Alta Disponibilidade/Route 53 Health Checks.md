Route 53 Health Checks são verificações usadas pelo [[Amazon Route 53]] para avaliar a saúde de endpoints.

Eles podem participar de estratégias de roteamento e failover em nível DNS.

Route 53 Health Checks ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Route 53 Health Checks pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

Route 53 Health Checks existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Como Funcionam**

Um health check pode verificar se um endpoint responde corretamente.

Se o endpoint falha, o Route 53 pode deixar de retornar aquele destino em certas políticas de roteamento.

**Uso**

* failover entre regiões;
* failover entre ambientes;
* monitoramento de endpoints públicos;
* roteamento resiliente.

---

## Exemplo prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

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

DNS possui cache e TTL.

Failover via DNS não é instantâneo em todos os clientes. O [[DNS TTL]] influencia o tempo percebido de mudança.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

**Relação com Failover**

Com [[Failover Routing]], um endpoint primário pode ser usado enquanto saudável.

Se falhar, o DNS passa a direcionar para endpoint secundário.

CloudWatch Agent é o agente usado para coletar métricas, logs e traces de instâncias [[Amazon EC2]], servidores on-premise e aplicações em containers.

Ele complementa as métricas padrão dos serviços AWS.

---

## Visão geral

CloudWatch Agent ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Por que Usar

Algumas métricas internas do sistema operacional não aparecem automaticamente em todos os cenários.

Exemplo:

* uso de memória;
* uso de disco;
* processos;
* logs de aplicação;
* arquivos de log específicos.

---

## Funcionamento

O agente é instalado e configurado na instância ou servidor.

Depois, envia dados para o [[Amazon CloudWatch]].

---

## Relação com Auto Scaling

Métricas coletadas pelo agente podem ajudar a entender saturação real.

Por exemplo, CPU pode estar baixa, mas memória pode estar esgotada.

---

## Cuidado

O agente precisa de permissões IAM adequadas.

Também é necessário controlar volume de logs para evitar custo inesperado.

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

Este conceito pertence ao módulo de escalabilidade e alta disponibilidade.

## Ponto central

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

## Como Diferenciar

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

## Cuidado importante

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

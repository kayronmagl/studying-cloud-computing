CloudWatch Agent é o agente usado para coletar métricas, logs e traces de instâncias [[Amazon EC2]], servidores on-premise e aplicações em containers.

Ele complementa as métricas padrão dos serviços AWS.

CloudWatch Agent ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

CloudWatch Agent pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Algumas métricas internas do sistema operacional não aparecem automaticamente em todos os cenários.

Exemplo:

* uso de memória;
* uso de disco;
* processos;
* logs de aplicação;
* arquivos de log específicos.

---

## Como funciona

**Funcionamento**

O agente é instalado e configurado na instância ou servidor.

Depois, envia dados para o [[Amazon CloudWatch]].

---

## Exemplo prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

**Como Diferenciar**

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

---

## Cuidados

O agente precisa de permissões [[AWS Identity and Access Management (IAM)|IAM]] adequadas.

Também é necessário controlar volume de logs para evitar custo inesperado.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com Auto Scaling**

Métricas coletadas pelo agente podem ajudar a entender saturação real.

Por exemplo, CPU pode estar baixa, mas memória pode estar esgotada.

- [[Amazon EC2]]
- [[Amazon CloudWatch]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon EC2 Auto Scaling]]

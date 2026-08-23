Retries com Backoff Exponencial são tentativas de repetição com espera crescente entre elas.

Esse padrão é usado para lidar com falhas transitórias.

Retries com Backoff Exponencial ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

Retries com Backoff Exponencial pertence ao desenho de disponibilidade, crescimento e recuperação. O objetivo é manter a aplicação funcionando quando há aumento de demanda, falha parcial ou necessidade de trocar tráfego para outro recurso.

Escalabilidade é crescer ou reduzir capacidade. Alta disponibilidade é continuar funcionando apesar de falhas.

---

## Por que existe

Falhas temporárias podem acontecer por rede, throttling, indisponibilidade curta ou saturação momentânea.

Retry pode resolver sem intervenção humana.

---

## Como funciona

Exemplo:

* 1ª tentativa: falha.
* espera 1 segundo
* 2ª tentativa: falha.
* espera 2 segundos
* 3ª tentativa: falha.
* espera 4 segundos

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

Retry sem limite pode piorar incidentes.

Se muitos clientes repetem agressivamente, aumentam carga sobre um sistema já degradado.

Por isso, combine retries com jitter, limites e [[Circuit Breaker]].

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

---

## Relação com outras notas

**Relação com AWS**

Muitos [[AWS SDKs|SDKs]] AWS usam estratégias de retry.

Aplicações também devem aplicar retries com cuidado ao chamar bancos, [[APIs|APIs]] e serviços externos.

- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon EC2 Auto Scaling]]
- [[Amazon CloudWatch]]
- [[Circuit Breaker]]

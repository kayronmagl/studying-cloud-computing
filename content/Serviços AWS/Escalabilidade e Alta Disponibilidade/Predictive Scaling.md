Predictive Scaling é uma estratégia de escala que usa padrões históricos para antecipar demanda futura.

Em vez de reagir apenas quando uma métrica já subiu, o sistema tenta prever necessidade de capacidade antes do pico.

---

## Visão geral

Predictive Scaling ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Diferença para Scheduled Scaling

[[Scheduled Scaling]] usa horários definidos manualmente.

Predictive scaling usa previsão baseada em histórico.

---

## Exemplo

Uma aplicação recebe picos todos os dias às 9h.

Em vez de esperar CPU subir, predictive scaling pode preparar capacidade antes do pico esperado.

---

## Quando Ajuda

* tráfego com padrão recorrente;
* picos diários ou semanais;
* aplicações que demoram para inicializar;
* sistemas com demanda previsível, mas variável.

---

## Limite

Previsão não é certeza.

Eventos inesperados, campanhas, falhas ou ataques podem fugir do padrão histórico.

Por isso, predictive scaling deve ser combinado com [[Target Tracking Scaling]], alarmes e observabilidade.

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

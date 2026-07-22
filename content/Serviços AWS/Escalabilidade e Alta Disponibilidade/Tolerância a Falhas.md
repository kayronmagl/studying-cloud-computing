Tolerância a Falhas é a capacidade de um sistema continuar operando durante uma falha prevista, com impacto mínimo ou imperceptível para o usuário ou para o processo atendido.

Não significa que o sistema nunca falha. Também não significa tolerar qualquer quantidade de falhas simultâneas. A quantidade e o tipo de falhas toleradas dependem do desenho da arquitetura, dos componentes redundantes, das dependências compartilhadas e dos mecanismos de recuperação.


Tolerância a falhas é diferente de [[Alta Disponibilidade]]. Alta disponibilidade busca manter o serviço acessível e pode aceitar uma interrupção curta durante detecção, failover ou recuperação. Tolerância a falhas é mais exigente: o sistema deve continuar operando apesar da falha específica para a qual foi projetado.

Uma arquitetura pode ser altamente disponível sem ser totalmente tolerante a falhas. Por exemplo, um banco pode fazer failover para outro nó, mas a aplicação pode precisar reconectar e repetir uma transação.

---

## Estratégias

* redundância;
* múltiplas [[Availability Zones (AZ)]];
* load balancing;
* replicação;
* filas;
* health checks;
* retry;
* timeout;
* circuit breaker;
* failover.

---

## Exemplo AWS

Uma aplicação web executa instâncias em duas AZs.

Se uma instância falha, o [[Elastic Load Balancing]] pode parar de enviar tráfego para ela depois que o health check detectar o problema. O [[Amazon EC2 Auto Scaling]] pode criar uma substituta. Durante esse processo, pode haver degradação, perda de sessão ou redução temporária de capacidade, dependendo da aplicação.

---

## Relação com SPOF

Tolerância a falhas reduz [[Single Points of Failure (SPOF)]].

Qualquer componente único e indispensável precisa ser analisado como risco.

Redundância isolada não basta quando componentes redundantes compartilham a mesma dependência. Duas instâncias em AZs diferentes ainda podem falhar juntas se dependem de uma configuração incorreta, uma credencial expirada, um serviço regional indisponível ou uma única base de dados sem estratégia de recuperação. Esse é o problema das [[Falhas Correlacionadas]].

---

## Limites da tolerância

Uma arquitetura tolerante à falha de uma instância pode não tolerar falha simultânea de uma AZ, do banco de dados e de uma dependência externa. Por isso, a análise precisa declarar quais falhas são esperadas, quais são toleradas e quais ainda exigem recuperação manual ou estratégia de [[Disaster Recovery (DR)]].

Tolerância a falhas também depende de observabilidade. Sem [[Amazon CloudWatch]], alarmes, health checks e testes, a equipe pode não perceber que a redundância não está funcionando como esperado.

---

## Cuidados importantes

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

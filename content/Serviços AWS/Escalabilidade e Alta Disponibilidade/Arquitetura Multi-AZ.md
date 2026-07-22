Arquitetura Multi-AZ distribui componentes entre múltiplas [[Availability Zones (AZ)]] dentro da mesma região.

É um dos padrões mais importantes de [[Alta Disponibilidade]] na AWS.


O objetivo é reduzir o impacto de uma falha zonal. Uma AZ é um limite de isolamento de falhas; ao distribuir aplicação, rede e dados entre duas ou mais AZs, a arquitetura evita depender de um único local físico.

---

## Por que Usar

Uma AZ pode sofrer falha local.

Se toda a aplicação está em uma única AZ, a falha pode derrubar o sistema.

Distribuir recursos entre AZs reduz esse risco.

---

## Fluxo básico

```text
Usuário
  ↓
Balanceador de carga
  ├── Aplicação na AZ A
  └── Aplicação na AZ B
           ↓
Banco de dados com estratégia de redundância
```

O usuário acessa um endpoint da aplicação. O balanceador de carga distribui tráfego para instâncias saudáveis em mais de uma AZ. Se uma instância ou uma zona falha, health checks ajudam a parar o envio de tráfego para destinos problemáticos. O banco precisa ter uma estratégia de redundância coerente com os requisitos de consistência, recuperação e perda aceitável de dados.

Esse fluxo não significa continuidade sem interrupção. Pode haver tempo de detecção, reconexões, degradação de desempenho, perda de sessões e operações que precisam ser repetidas.

---

## Exemplo

Uma aplicação web pode usar:

* [[Application Load Balancer]] em sub-redes públicas de duas AZs;
* instâncias EC2 em sub-redes privadas de duas AZs;
* [[Auto Scaling Groups]] distribuídos;
* [[Amazon RDS]] com [[Multi-AZ]];
* [[Amazon CloudWatch]] para alarmes.

---

## Relação com Rede

Multi-AZ depende de [[Redes na AWS]] bem desenhadas.

Subnets precisam existir em múltiplas zonas. Route tables, security groups e load balancers precisam refletir esse desenho.

Também é necessário planejar capacidade. Se uma AZ falhar, as AZs restantes precisam ter recursos suficientes para atender a carga essencial. Caso contrário, a aplicação pode continuar parcialmente disponível, mas com lentidão, filas maiores ou erros.

---

## Dados e failover

Multi-AZ envolve mais do que distribuir computação. Dados precisam ser replicados, restauráveis ou reconstruíveis conforme o serviço usado.

Replicação síncrona pode reduzir perda de dados, mas pode aumentar latência de escrita. Replicação assíncrona pode reduzir impacto na escrita, mas admite atraso e risco de perda conforme o [[Recovery Point Objective (RPO)]]. O [[Recovery Time Objective (RTO)]] define quanto tempo de recuperação é aceitável.

[[Failover]] não é sinônimo de replicação. Failover é a transferência da operação para outro recurso ou zona. Replicação é o mecanismo que mantém dados disponíveis no destino.

---

## Trade-offs

Distribuir recursos entre AZs aumenta resiliência, mas pode adicionar custo, complexidade operacional, tráfego entre zonas, latência entre componentes e possíveis cobranças de transferência de dados.

Também não remove [[Single Points of Failure (SPOF)]] automaticamente. Uma dependência regional, configuração compartilhada, credencial, pipeline de deploy, banco mal desenhado ou serviço externo único ainda pode derrubar a aplicação.

---

## Cuidado

Multi-AZ não é o mesmo que multi-region.

Se a região inteira falhar, Multi-AZ dentro daquela região pode não bastar. Nesses casos, a análise passa para [[Arquitetura Multi-Region]], [[Disaster Recovery (DR)]] e requisitos de negócio.

---

## Cuidados importantes

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

## Como entender isso

Este conceito pertence ao módulo de escalabilidade e alta disponibilidade.

## Ponto central

Escalabilidade é crescer ou reduzir capacidade. Arquitetura Multi-AZ usa isolamento entre zonas para reduzir o impacto de falhas locais.

## Como Diferenciar

* CloudWatch observa.
* Auto Scaling ajusta capacidade.
* ELB distribui tráfego.
* Health checks removem destinos ruins.
* Multi-AZ reduz falha zonal.
* RTO e RPO guiam recuperação.

## Cuidado importante

Auto Scaling não garante alta disponibilidade sozinho. Precisa de múltiplas AZs, load balancing e health checks.

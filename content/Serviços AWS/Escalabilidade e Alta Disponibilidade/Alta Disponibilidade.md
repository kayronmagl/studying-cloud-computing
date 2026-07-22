Alta Disponibilidade é uma propriedade arquitetural que busca manter um serviço acessível mesmo quando componentes falham.

Em AWS, alta disponibilidade normalmente envolve distribuir componentes entre múltiplas [[Availability Zones (AZ)]], reduzir [[Single Points of Failure (SPOF)]], usar balanceamento, health checks, replicação, observabilidade e mecanismos de recuperação.

---

## Visão geral

Alta disponibilidade não é consequência automática de hospedar uma aplicação na AWS. Ela depende de como a aplicação, os dados, a rede, as permissões, a capacidade e os mecanismos de recuperação foram desenhados.

---

## Objetivo

O objetivo não é impedir toda falha.

Falhas acontecem.

O objetivo é reduzir interrupções e impedir que uma falha isolada derrube o serviço inteiro. Mesmo em uma arquitetura bem desenhada, podem existir tempo de detecção, tempo de failover, reconexões, perda de sessões, indisponibilidade parcial, degradação de desempenho e operações que precisam ser repetidas.

---

## Componentes

Alta disponibilidade usa:

* redundância;
* múltiplas AZs;
* health checks;
* load balancers;
* failover;
* replicação;
* backups;
* monitoramento;
* automação;
* bancos Multi-AZ.

---

## Exemplo

Uma aplicação com uma única instância EC2 tem baixa disponibilidade.

Uma aplicação com várias instâncias em múltiplas AZs, atrás de um [[Application Load Balancer]], com [[Auto Scaling Groups]] e banco [[Multi-AZ]], possui disponibilidade maior. Isso não garante funcionamento sem interrupção; o resultado depende de health checks corretos, capacidade suficiente nas AZs restantes, dados recuperáveis e aplicação preparada para reconectar.

---

## Relação com Resiliência

[[Resiliência]] inclui alta disponibilidade, recuperação, tolerância a falhas e capacidade de adaptação.

Alta disponibilidade é um subconjunto importante da resiliência.

Alta disponibilidade também não é o mesmo que [[Tolerância a Falhas]]. A alta disponibilidade aceita a possibilidade de uma interrupção curta enquanto o sistema detecta a falha e se recupera. Tolerância a falhas busca manter operação durante a falha com impacto mínimo ou imperceptível, conforme o tipo de falha para o qual a arquitetura foi desenhada.

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

Possuir várias AZs disponíveis na região também não distribui automaticamente todos os recursos. Alguns serviços regionais usam múltiplas AZs internamente, mas recursos zonais e várias decisões de arquitetura exigem configuração explícita do cliente.

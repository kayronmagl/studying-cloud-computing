Design à Prova de Falhas é um princípio arquitetural em que sistemas são desenhados assumindo que falhas vão acontecer.

Em vez de tentar impedir toda falha, a arquitetura reduz impacto e se recupera.

Na nuvem, você deve projetar como se componentes fossem falhar.

Instâncias podem cair. Uma zona pode ter problema. Uma rede pode oscilar. Um serviço pode degradar.

Boa arquitetura não depende de tudo funcionar perfeitamente o tempo todo.

---

## O que é

Design à prova de falhas significa projetar aceitando que coisas vão quebrar.

Uma pergunta não é “e se falhar?”.

Uma pergunta é “quando falhar, o que acontece?”.

Design à prova de falhas é criar sistemas que continuam funcionando, ou se recuperam rapidamente, quando componentes falham.

---

## Por que existe

Design à Prova de Falhas existe para orientar decisões que não são apenas técnicas. Adoção de nuvem envolve pessoas, processos, risco, plataforma, segurança, operação, custo e valor de negócio.

---

## Como funciona

**Pensando como arquiteto**

Quando você distribui uma aplicação em várias zonas de disponibilidade, você está dizendo:

* não quero que uma falha local derrube tudo

Esse é o espírito do design à prova de falhas.

A AWS oferece regiões e zonas, mas você precisa usar isso corretamente. Se colocar tudo em uma única instância, em uma única zona, com um único banco sem estratégia de recuperação, a aplicação continua frágil.

---

## Exemplo prático

* usar múltiplas [[Availability Zones (AZ)]];
* usar [[Elastic Load Balancing]];
* configurar health checks;
* usar backups;
* definir RTO e RPO;
* desacoplar com [[Amazon SQS]];
* automatizar substituição de recursos com Auto Scaling.

Uma aplicação em uma única instância [[Amazon EC2|EC2]] pode parar se aquela instância falhar.

Uma aplicação em múltiplas zonas, atrás de um load balancer, tem mais chance de continuar funcionando.

**Exemplo de Resposta**

Quando surgir um cenário perguntar:

* qual princípio combina com distribuir cargas de trabalho em várias zonas de disponibilidade?

Você deve pensar:

* isso reduz o impacto de falhas
* logo, é design à prova de falhas

---

## Diferenças importantes

**Pontos que Costumam Gerar Confusão**

O cenário descreve qual princípio é compatível com distribuir workloads em várias zonas de disponibilidade.

A resposta é Design à prova de falhas.

**Como Diferenciar**

Quando o cenário envolve distribuir workloads em várias zonas de disponibilidade, ela está falando de reduzir impacto de falhas.

A resposta é Design à prova de falhas.

**Diferença importante**

* [[Elasticidade]]: crescer e reduzir conforme demanda.
* Design à prova de falhas: continuar funcionando quando algo falha.

As duas coisas podem andar juntas, mas não são iguais.

---

## Cuidados

Distribuir em várias AZs não é apenas elasticidade.

Elasticidade é ajustar capacidade.

Design à prova de falhas é reduzir impacto quando algo falha.

---

## Relação com outras notas

- [[Availability Zones (AZ)]]
- [[Elastic Load Balancing]]
- [[Amazon SQS]]
- [[Elasticidade]]

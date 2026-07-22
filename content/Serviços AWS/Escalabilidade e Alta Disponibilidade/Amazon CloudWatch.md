Amazon CloudWatch é o serviço de observabilidade e monitoramento da AWS.

Ele coleta, armazena e apresenta métricas, logs, alarmes, dashboards e sinais operacionais de serviços AWS, aplicações e infraestrutura.

CloudWatch é essencial para [[Escalabilidade e Alta Disponibilidade na AWS]] porque muitos mecanismos de escala e resposta dependem de sinais observáveis.


Amazon CloudWatch ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.


---

## Como Funciona

O funcionamento pode ser entendido assim:


* serviços AWS ou aplicações: ↓.
* métricas, logs e eventos: ↓.
* Amazon CloudWatch: ↓.
* dashboards, alarmes, consultas e ações


Serviços como [[Amazon EC2]], [[Amazon EBS]], [[Amazon RDS]] e [[AWS Lambda]] publicam métricas. Aplicações podem publicar métricas customizadas. O [[CloudWatch Agent]] coleta métricas e logs adicionais de instâncias, servidores e containers.

---

## Métricas

[[Métricas do Amazon CloudWatch]] representam valores numéricos ao longo do tempo.

Exemplos:

* CPU;
* latência;
* erros;
* requisições;
* tamanho de fila;
* conexões de banco;
* uso de disco;
* duração de função Lambda.

---

## Logs

[[Logs do Amazon CloudWatch]] centralizam eventos textuais e estruturados de aplicações e serviços.

Logs explicam o comportamento por trás das métricas.

---

## Alarmes

[[Alarmes do Amazon CloudWatch]] observam métricas e executam ações quando condições são atingidas.

Um alarme pode notificar uma equipe ou acionar uma política do [[Amazon EC2 Auto Scaling]].

---

## Dashboards

[[Dashboards do Amazon CloudWatch]] organizam visualmente métricas e gráficos.

Eles ajudam a entender comportamento de sistemas distribuídos.

---

## Relação com Auto Scaling

CloudWatch fornece sinais. Auto Scaling age sobre esses sinais.

Exemplo: se CPU média fica alta por vários minutos, um alarme pode acionar expansão do Auto Scaling Group.

---

## Cuidado

Monitorar tudo sem critério gera ruído.

O ideal é escolher métricas que representem saúde real da aplicação, como latência, taxa de erro, saturação e throughput.

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

## Explicação principal

Amazon CloudWatch é o serviço de observabilidade da AWS.

Ele coleta métricas, logs, alarmes e dashboards.

## Como Funciona na prática

Serviços AWS publicam métricas. Aplicações e agentes podem enviar logs e métricas customizadas. Alarmes observam métricas e disparam ações.

## Usos

* monitorar CPU de EC2;
* acompanhar latência de ALB;
* registrar logs de Lambda;
* criar alarmes de erro;
* acionar Auto Scaling;
* montar dashboards operacionais.

## Diferença Importante

CloudWatch mostra comportamento operacional.

CloudTrail mostra ações de API e auditoria.

## Cuidado importante

Ter logs não significa ter observabilidade. É preciso escolher métricas, alarmes e dashboards que indiquem saúde real da aplicação.

---

## Na prática

CloudWatch é onde você observa sinais do sistema.

Se a aplicação fosse uma pessoa, CloudWatch mediria temperatura, batimento, respiração e alertaria se algo passasse do limite.

Em AWS, esses sinais são métricas, logs, alarmes e dashboards.

---

## Exemplo

Você pode criar alarme para:

* CPU alta em EC2;
* erro em Lambda;
* fila SQS crescendo demais;
* billing passando de um limite;
* latência alta em load balancer.

---

## Como Diferenciar

Quando o cenário envolve:


* monitorar
* métricas
* logs
* alarmes
* notificação quando limite é excedido


pense em Amazon CloudWatch.

---

## CloudWatch vs CloudTrail

* CloudWatch: observa comportamento do sistema.
* [[AWS CloudTrail|CloudTrail]]: registra ações feitas na conta.


Essa diferença cai muito.

---

## Alarmes e custos

Além de métricas operacionais, [[Alarmes de Faturamento com Amazon CloudWatch]] aparecem quando uma pergunta que fala em aviso por limite de billing.

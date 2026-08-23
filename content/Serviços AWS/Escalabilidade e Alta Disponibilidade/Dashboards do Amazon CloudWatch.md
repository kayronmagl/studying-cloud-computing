Dashboards do Amazon CloudWatch são painéis visuais para acompanhar métricas e estado operacional de recursos.

Eles ajudam a reunir sinais de múltiplos serviços em uma visão única.

Dashboards do Amazon CloudWatch ajuda a responder duas perguntas: “como o sistema cresce?” e “como ele continua funcionando quando algo falha?”.

---

## O que é

[[Amazon RDS]] é o serviço gerenciado de bancos relacionais da AWS.

Ele suporta motores como MySQL, PostgreSQL, MariaDB, Oracle, SQL Server e outros conforme disponibilidade.

---

## Por que existe

Dashboards do Amazon CloudWatch existe para manter aplicações disponíveis, responsivas e recuperáveis quando há aumento de demanda, falhas ou variações no ambiente. Sem esse tipo de desenho, crescimento e falha viram eventos manuais e arriscados.

---

## Como funciona

**Função**

Dashboards permitem visualizar:

* latência;
* taxa de erro;
* requisições;
* CPU;
* uso de banco;
* tamanho de filas;
* status de alarmes;
* capacidade de Auto Scaling.

**Uso**

Uma equipe pode criar um dashboard para produção contendo:

* métricas do [[Elastic Load Balancing]];
* métricas do [[Amazon EC2 Auto Scaling]];
* métricas do [[Amazon RDS]];
* erros da aplicação;
* logs relevantes;
* alarmes críticos.

**O que a AWS Gerencia**

* provisionamento;
* backups automáticos;
* patches do mecanismo em certos cenários;
* armazenamento;
* snapshots;
* Multi-AZ;
* monitoramento básico.

**O que o Cliente Ainda Gerencia**

* modelo de dados;
* queries;
* índices;
* usuários do banco;
* permissões;
* parâmetros;
* performance da aplicação.

---

## Exemplo prático

Uma aplicação pode ser distribuída em múltiplas [[Availability Zones (AZ)]], atrás de um [[Application Load Balancer]], com instâncias gerenciadas por [[Amazon EC2 Auto Scaling]] e métricas no [[Amazon CloudWatch]].

Quando a carga aumenta, novas instâncias entram. Quando uma falha ocorre, destinos não saudáveis são removidos.

---

## Diferenças importantes

Não confunda escalabilidade, disponibilidade e resiliência. Escalabilidade lida com variação de demanda, disponibilidade lida com acesso contínuo e resiliência lida com sobreviver e recuperar após falhas.

---

## Cuidados

Dashboard bonito não significa observabilidade útil.

Um bom dashboard responde perguntas operacionais reais.

Escalar sem observar pode aumentar custo.

Ter múltiplas instâncias sem health check pode manter falhas ativas.

Ter alta disponibilidade sem testes pode criar falsa confiança.

Por isso, esses conceitos devem ser combinados com métricas, alarmes, limites e testes de resiliência.

[[Amazon RDS|RDS]] gerencia o banco, mas não cria automaticamente uma boa modelagem. Query ruim continua sendo query ruim.

---

## Relação com outras notas

**Relação com Operação**

Dashboards ajudam durante incidentes, deploys, picos de tráfego e análises de performance.

- [[Amazon RDS]]
- [[Elastic Load Balancing]]
- [[Amazon EC2 Auto Scaling]]
- [[Availability Zones (AZ)]]
- [[Application Load Balancer]]
- [[Amazon CloudWatch]]

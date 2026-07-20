Amazon Timestream é a família de serviços da AWS voltada a dados organizados ao longo do tempo, como métricas, telemetria, sensores, eventos operacionais e medições de IoT.

---

## Timestream for LiveAnalytics

Amazon Timestream for LiveAnalytics é um banco de séries temporais serverless, criado para ingestão em grande escala, retenção por camadas e consultas baseadas em janelas de tempo.

Desde 20 de junho de 2025, o serviço não aceita novos clientes. Contas pagadoras que já o utilizavam podem continuar criando recursos e adicionando contas vinculadas conforme as regras da AWS.

Para novos clientes, a AWS recomenda avaliar o Amazon Timestream for InfluxDB.

---

## Modelo de Dados

Em uma série temporal, o timestamp é parte central do registro. Dimensões identificam a origem ou o contexto, enquanto medidas armazenam valores observados.

Exemplos:

* uso de CPU por segundo;
* temperatura de um sensor por minuto;
* telemetria de veículos;
* métricas financeiras;
* eventos de aplicações;
* medições industriais.

---

## Quando um Banco de Séries Temporais Ajuda

Esse modelo é adequado quando as consultas dependem de intervalos, agregações temporais, médias móveis, retenção e grande volume de escrita sequencial.

É possível armazenar esse tipo de dado no [[Amazon RDS]] ou no [[Amazon DynamoDB]], mas a modelagem, o custo e o desempenho podem ser menos adequados conforme o volume cresce. A nota [[Bancos de Dados de Séries Temporais]] aprofunda essa diferença.

---

## Cuidados

A modelagem precisa considerar cardinalidade, granularidade, retenção, frequência de ingestão e padrão de consulta. Um serviço especializado não elimina a necessidade de entender quais dimensões serão filtradas e quais agregações a aplicação executará.

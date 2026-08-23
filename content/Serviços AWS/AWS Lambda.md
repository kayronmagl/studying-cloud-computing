AWS Lambda é o serviço [[Computação sem Servidor (Serverless)|serverless]] da AWS usado para executar código em resposta a eventos, chamadas diretas ou integrações com outros serviços.

A ideia central é simples: em vez de criar uma [[Instância EC2]], instalar sistema operacional, configurar runtime, manter processo rodando e escalar servidores, o usuário publica uma função. A AWS prepara ambientes de execução, invoca o código quando necessário, escala a quantidade de execuções e envia sinais operacionais para o [[Amazon CloudWatch]].

Lambda não elimina servidores. Ele remove o gerenciamento direto dos servidores pelo cliente.

---

## O que é

Você não provisiona servidor antes.

Você envia código, configura execução e paga por invocações/duração.

---

## Por que existe

Em uma aplicação tradicional hospedada em [[Amazon EC2]], a equipe precisa responder perguntas como:

* quantas instâncias devo manter ligadas?
* qual tipo de instância usar?
* como aplicar patches no sistema operacional?
* como escalar em picos?
* como recuperar se uma instância falhar?
* como manter capacidade sem pagar por ociosidade?

No Lambda, a unidade de raciocínio muda.

A equipe passa a perguntar:

* qual evento dispara o código?
* qual função processa esse evento?
* qual timeout é adequado?
* quanta memória a função precisa?
* quais permissões [[AWS Identity and Access Management (IAM)|IAM]] são necessárias?
* como tratar retries e duplicidade?
* como observar logs, erros e duração?

Essa mudança é importante para quem está aprendendo nuvem: o foco sai da máquina e vai para evento, função, permissão, execução e observabilidade.

---

## Como funciona

**Como o Lambda Funciona**

O fluxo básico de uma execução Lambda é:

* evento de entrada: ↓.
* invocação da função: ↓.
* preparação ou reutilização do ambiente: ↓.
* execução do runtime: ↓.
* chamada do handler: ↓.
* uso de permissões via execution role: ↓.
* retorno, erro ou publicação de saída: ↓.
* logs e métricas no CloudWatch

Cada parte desse fluxo precisa ser entendida separadamente.

**Evento**

Um evento é o dado de entrada que chega à função.

Ele pode representar:

* uma requisição HTTP do [[Amazon API Gateway]];
* um upload em [[Amazon S3]];
* uma mensagem do [[Amazon SQS]];
* um evento roteado pelo [[Amazon EventBridge]];
* uma etapa coordenada pelo [[AWS Step Functions]];
* uma chamada direta por [[AWS SDKs]] ou [[APIs]].

O formato do evento depende da origem. Um evento do [[APIs|API]] Gateway contém método HTTP, headers, path, query string e corpo da requisição. Um evento do [[Amazon S3|S3]] contém [[Buckets S3|bucket]], chave do objeto e metadados do arquivo. Um evento do [[Amazon SQS|SQS]] contém uma lista de mensagens.

**Invocação**

A invocação é a chamada da função.

Existem três formas importantes de pensar nisso:

### Invocação síncrona

O cliente chama a função e espera resposta.

Exemplo: [[APIs|API]] Gateway chama Lambda para responder `GET /produtos`.

Se a função demora, o usuário espera. Se a função falha, o cliente recebe erro.

### Invocação assíncrona

O evento é aceito para processamento, mas o chamador não espera o resultado direto.

Exemplo: um evento é enviado para processar uma imagem ou enviar uma notificação.

Nesse modelo, retries e destinos de falha/importância operacional precisam ser configurados com cuidado.

### Event Source Mapping

Em [[Event Source Mapping]], o próprio Lambda lê registros de fontes como [[Amazon SQS]] ou streams e invoca a função com lotes de dados.

Isso é fundamental para processamento assíncrono e desacoplado.

**Ambiente de Execução**

O ambiente de execução é o espaço preparado pela AWS para rodar a função.

Ele contém runtime, código, dependências e contexto necessário para executar o handler.

Quando a AWS precisa criar um ambiente novo, pode ocorrer [[Cold Start]]. Quando o ambiente é reutilizado, ocorre uma execução aquecida, normalmente mais rápida.

Isso explica por que inicializações pesadas, bibliotecas grandes e conexões mal gerenciadas podem afetar latência.

**Runtime**

O runtime é o suporte da linguagem usada pela função.

Exemplos:

* Python;
* Node.js;
* Java;
* Go;
*. NET;
* Ruby;
* runtimes customizados.

O runtime carrega o código e chama o handler.

**Handler**

O handler é o ponto de entrada da função.

Exemplo conceitual em Python:

```python
def handler(event, context):
    return {"status": "ok"}
```

O `event` contém os dados da invocação. O `context` contém metadados da execução, como tempo restante, identificador da requisição e informações do ambiente.

O handler deve ser pequeno o suficiente para ser compreensível, mas não tão fragmentado a ponto de criar dezenas de funções difíceis de rastrear.

**Execution Role**

Toda função Lambda executa com uma role do [[AWS Identity and Access Management (IAM)|IAM]], chamada de execution role.

Essa role define o que a função pode fazer.

Exemplo:

* ler objetos de um [[Buckets S3|bucket]] [[Amazon S3]];
* escrever logs no [[Amazon CloudWatch]];
* enviar mensagens para [[Amazon SQS]];
* publicar eventos no [[Amazon EventBridge]];
* acessar um banco [[Amazon RDS]];
* chamar outro serviço AWS.

Sem permissão, a função pode até iniciar, mas falhará ao tentar acessar o recurso.

Isso conecta Lambda diretamente ao [[Modelo de Responsabilidade Compartilhada]]: a AWS executa a infraestrutura, mas o cliente define permissões corretas.

**Concorrência**

[[Concorrência Lambda]] é a quantidade de execuções simultâneas da função.

Se muitos eventos chegam ao mesmo tempo, o Lambda pode executar várias cópias da função em paralelo.

Isso é poderoso, mas perigoso quando a função chama recursos limitados.

Exemplo: uma função que processa mensagens do [[Amazon SQS|SQS]] e grava no [[Amazon RDS|RDS]] pode escalar rapidamente e abrir conexões demais no banco. Nesse caso, limitar concorrência pode proteger o sistema.

**Cold Start**

[[Cold Start]] é a latência adicional quando um novo ambiente de execução precisa ser criado.

Pode ser afetado por:

* linguagem usada;
* tamanho do pacote;
* dependências;
* inicialização fora do handler;
* conexão com [[Amazon VPC|VPC]];
* provisioned concurrency;
* complexidade do código.

Cold start costuma importar mais em [[APIs|APIs]] síncronas sensíveis a latência. Em processamento assíncrono por fila, geralmente é menos crítico.

**Retries, Erros e DLQ**

Lambda precisa ser desenhado para falhas.

Eventos podem ser repetidos. Chamadas podem falhar. Serviços externos podem estar indisponíveis. Mensagens podem ser entregues mais de uma vez.

Por isso, três conceitos são essenciais:

* [[Idempotência]];
* [[Dead Letter Queue (DLQ)]];
* retries controlados.

Exemplo: se uma função processa pagamento, ela não pode cobrar duas vezes apenas porque recebeu o mesmo evento novamente.

**Observabilidade**

Toda função Lambda precisa ser observável.

O mínimo esperado é:

* logs estruturados no [[Amazon CloudWatch]];
* métricas de duração;
* métricas de erro;
* métricas de concorrência;
* alarmes;
* rastreamento de requisições;
* correlação por identificador de evento.

Sem observabilidade, serverless vira uma caixa-preta difícil de depurar.

**Exemplo Completo**

Um sistema de imagens pode funcionar assim:

1. Usuário envia imagem para uma [[APIs|API]] no [[Amazon API Gateway]].
2. [[APIs|API]] Gateway invoca uma função Lambda.
3. A função valida autenticação e tamanho do arquivo.
4. A imagem é salva no [[Amazon S3]].
5. O evento do [[Amazon S3|S3]] aciona outra função Lambda.
6. A segunda função gera miniaturas.
7. Uma mensagem é enviada ao [[Amazon SQS]].
8. Falhas repetidas vão para uma [[Dead Letter Queue (DLQ)]].
9. O [[Amazon CloudFront]] entrega imagens otimizadas.
10. O [[Amazon CloudWatch]] registra logs, métricas e alarmes.

Esse exemplo mostra o papel real do Lambda: ele não é apenas “código sem servidor”. Ele é uma peça de execução orientada a eventos dentro de uma arquitetura distribuída.

**Funções sob demanda**

O Lambda é um exemplo direto de [[Function as a Service (FaaS)]], porque executa código em funções acionadas por eventos.

---

## Exemplo prático

Em uma arquitetura simples, usuário, aplicação, rede, banco, armazenamento, segurança e monitoramento trabalham juntos. AWS Lambda deve ser entendido pelo papel que exerce nesse conjunto.

---

## Diferenças importantes

**Quando Usar**

Lambda funciona bem para:

* [[APIs|APIs]] leves;
* automações;
* processamento de arquivos;
* tarefas agendadas;
* integração entre serviços;
* eventos assíncronos;
* pipelines;
* workloads variáveis;
* protótipos que precisam escalar sem operar servidores.

**Quando Evitar**

Lambda pode não ser ideal para:

* processos muito longos;
* workloads contínuos;
* aplicações que exigem controle profundo do sistema operacional;
* conexões persistentes complexas;
* cargas com latência extremamente previsível;
* dependências nativas pesadas;
* processamento que excede limites de timeout.

Nesses casos, [[Amazon EC2]], [[Amazon ECS]], [[Amazon EKS]] ou [[AWS Fargate]] podem ser melhores.

**Pontos que Costumam Gerar Confusão**

A afirmação verdadeira sobre Lambda é que a empresa paga apenas pelo tempo de computação durante a execução do código.

---

## Cuidados

Lambda não exige configurar servidores.

A primeira etapa não é provisionar servidor.

Serverless não significa sem infraestrutura; significa sem gerenciamento direto de servidores.

---

## Relação com outras notas

- [[Computação sem Servidor (Serverless)]]
- [[Instância EC2]]
- [[Amazon CloudWatch]]
- [[Amazon EC2]]
- [[Amazon API Gateway]]
- [[Amazon S3]]
- [[Amazon SQS]]
- [[Amazon EventBridge]]
- [[AWS Step Functions]]
- [[AWS SDKs]]

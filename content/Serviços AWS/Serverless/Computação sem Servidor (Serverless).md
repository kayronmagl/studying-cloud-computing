Computação sem Servidor, ou Serverless, é um modelo de computação em nuvem em que o cliente executa código, containers, eventos, filas ou workflows sem gerenciar diretamente servidores, sistemas operacionais, clusters ou capacidade física.

O nome não deve ser interpretado literalmente. Servidores continuam existindo nos [[Data Centers]], nas [[Availability Zones (AZ)]] e nas [[Regions (Regiões)]]. O que muda é a fronteira de responsabilidade: o provedor gerencia mais da infraestrutura operacional, e o cliente foca mais no comportamento da aplicação.

Na AWS, o serviço mais importante para entender serverless é o [[AWS Lambda]].

---

## Visão geral

Computação sem Servidor (Serverless) faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## Ideia Central

Em modelos tradicionais, o raciocínio começa pela máquina.


* preciso de um servidor
* preciso escolher CPU e memória
* preciso instalar sistema operacional
* preciso manter runtime
* preciso escalar capacidade


Em serverless, o raciocínio começa pelo evento ou unidade de trabalho.


* algo aconteceu
* uma função deve reagir
* uma fila deve absorver o pico
* um workflow deve coordenar etapas
* um container deve executar sem cluster próprio


Esse deslocamento é a chave conceitual.

---

## Serverless não é Apenas Lambda

[[AWS Lambda]] é o exemplo mais conhecido, mas serverless também aparece em outros formatos:

* [[AWS Fargate]] para containers sem gerenciar servidores;
* [[Amazon API Gateway]] para expor APIs sem manter servidor web próprio;
* [[Amazon EventBridge]] para roteamento de eventos;
* [[Amazon SQS]] para filas gerenciadas;
* [[Amazon SNS]] para publicação e assinatura;
* [[AWS Step Functions]] para workflows;
* [[Amazon S3]] como armazenamento orientado a eventos;
* [[Amazon CloudWatch]] para logs, métricas e alarmes.

Serverless é uma família de padrões operacionais, não um único serviço.

---

## O que o Cliente Ainda Gerencia

Serverless reduz operação, mas não elimina responsabilidade técnica.

O cliente ainda precisa cuidar de:

* permissões no [[AWS Identity and Access Management (IAM)|IAM]];
* desenho de eventos;
* contratos entre serviços;
* validação de entrada;
* tratamento de erro;
* [[Idempotência]];
* retries;
* [[Dead Letter Queue (DLQ)]];
* custo;
* observabilidade;
* segurança;
* limites de serviço;
* dependências externas;
* arquitetura de dados.

O provedor remove parte da carga operacional, mas não substitui engenharia.

---

## Relação com Pay-as-you-go

Serverless combina bem com [[Pay-as-you-go]] porque muitos serviços cobram por invocação, duração, mensagens, transições de estado, requisições ou volume processado.

Isso é útil para cargas variáveis.

Exemplo: uma função que roda cem vezes por dia não precisa manter um servidor ligado vinte e quatro horas. Ela executa quando necessário.

Mas o custo pode crescer se houver alto volume, loops de eventos, retries mal controlados ou payloads grandes.

---

## Pontos Fortes

Serverless é forte quando o sistema precisa de:

* elasticidade rápida;
* baixa operação de infraestrutura;
* integração entre serviços;
* processamento assíncrono;
* automação;
* arquitetura orientada a eventos;
* redução de capacidade ociosa;
* experimentação rápida.

---

## Pontos Fracos

Serverless pode ser ruim quando o sistema exige:

* execução longa;
* controle profundo do sistema operacional;
* latência extremamente previsível;
* runtime muito específico;
* processos sempre ativos;
* dependências pesadas;
* conexão persistente complexa;
* debugging local idêntico ao ambiente real.

Nesses casos, serviços como [[Amazon EC2]], [[Amazon ECS]], [[Amazon EKS]] ou [[AWS Fargate]] podem ser mais adequados.

---

## Exemplo de Leitura Arquitetural

Um upload de imagem pode acionar um fluxo completo:


* [[Amazon API Gateway]]: ↓.
* [[AWS Lambda]]: ↓.
* [[Amazon S3]]: ↓.
* evento: ↓.
* [[AWS Lambda]]: ↓.
* [[Amazon SQS]]: ↓.
* [[AWS Step Functions]]: ↓.
* Amazon CloudWatch


Cada serviço cumpre um papel. O aprendizado correto é enxergar as conexões entre eles, não decorar nomes.

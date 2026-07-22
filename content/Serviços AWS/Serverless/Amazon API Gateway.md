Amazon API Gateway é o serviço da AWS para criar, publicar, proteger, monitorar e operar APIs.

Em arquiteturas serverless, ele costuma ser a porta de entrada HTTP para funções [[AWS Lambda]]. O usuário externo chama uma URL HTTPS, o API Gateway recebe a requisição, aplica regras e encaminha a chamada para o backend configurado.


Amazon API Gateway faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## Papel na Arquitetura

API Gateway fica entre o cliente e a lógica de aplicação.

Ele pode cuidar de:

* roteamento;
* métodos HTTP;
* paths;
* autenticação;
* autorização;
* validação;
* limites de taxa;
* transformação de payload;
* integração com Lambda;
* logs e métricas;
* controle de versões;
* CORS.

Isso evita manter um servidor web próprio apenas para receber requisições e chamar funções.

---

## Integração com Lambda

O padrão mais comum é:


* cliente HTTP: ↓.
* Amazon API Gateway: ↓.
* [[AWS Lambda]]: ↓.
* serviços internos


Em uma integração proxy com Lambda, o API Gateway envia para a função um evento contendo headers, path, query string, método HTTP, corpo e contexto da requisição.

A função processa e devolve uma resposta no formato esperado.

---

## HTTP API vs REST API

A AWS possui modelos diferentes de APIs.

Em termos didáticos:

* HTTP APIs: mais simples, geralmente mais baratas e com menos recursos avançados.
* REST APIs: mais antigas e com mais recursos de controle, validação, API keys e cenários complexos.

A escolha depende da necessidade de recursos e do custo.

---

## Segurança

API Gateway pode ser protegido por:

* IAM;
* autorizadores Lambda;
* tokens JWT;
* API keys;
* throttling;
* [[AWS WAF]];
* HTTPS;
* políticas de recurso.

O erro comum é expor uma função sem pensar em autenticação, limites e logs.

---

## Exemplo

Uma API de cadastro usa:

1. `POST /usuarios` no API Gateway.
2. Integração com [[AWS Lambda]].
3. Lambda valida entrada.
4. Lambda grava no [[Amazon RDS]].
5. Lambda publica evento no [[Amazon EventBridge]].
6. Logs e métricas vão para [[Amazon CloudWatch]].

API Gateway é a porta. Lambda é a execução. RDS é persistência. EventBridge distribui eventos. CloudWatch observa.

## Como entender isso

Este conceito pertence à camada de rede na AWS.

## Ponto central

A VPC define isolamento lógico. Subnets dividem a VPC por zona. Route tables definem caminhos. Gateways conectam a VPC a redes externas ou serviços.

## Como Diferenciar

* Subnet pertence a uma única AZ.
* VPC é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

## Cuidado importante

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

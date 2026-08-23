Amazon [[APIs|API]] Gateway é o serviço da AWS para criar, publicar, proteger, monitorar e operar [[APIs|APIs]].

Em arquiteturas serverless, ele costuma ser a porta de entrada HTTP para funções [[AWS Lambda]]. O usuário externo chama uma URL HTTPS, o [[APIs|API]] Gateway recebe a requisição, aplica regras e encaminha a chamada para o backend configurado.

Amazon [[APIs|API]] Gateway faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## O que é

Amazon API Gateway deve ser entendido como execução ou integração sem administração direta de servidores. Os servidores continuam existindo, mas a equipe trabalha mais perto de eventos, funções, limites e configuração do serviço.

A [[Amazon VPC|VPC]] define isolamento lógico. Subnets dividem a [[Amazon VPC|VPC]] por zona. Route tables definem caminhos. Gateways conectam a [[Amazon VPC|VPC]] a redes externas ou serviços.

---

## Por que existe

Amazon [[APIs|API]] Gateway existe para reduzir a administração direta de servidores e aproximar execução de eventos, demanda real e automação. O ganho aparece quando a arquitetura aceita unidades menores, acoplamento controlado e observabilidade.

---

## Como funciona

**Papel na Arquitetura**

[[APIs|API]] Gateway fica entre o cliente e a lógica de aplicação.

Ele pode cuidar de:

* roteamento;
* métodos HTTP;
* paths;
* autenticação;
* autorização;
* validação;
* limites de taxa;
* transformação de payload;
* integração com [[AWS Lambda|Lambda]];
* logs e métricas;
* controle de versões;
* CORS.

Isso evita manter um servidor web próprio apenas para receber requisições e chamar funções.

**Integração com [[AWS Lambda|Lambda]]**

O padrão mais comum é:

* cliente HTTP: ↓.
* Amazon [[APIs|API]] Gateway: ↓.
* [[AWS Lambda]]: ↓.
* serviços internos

Em uma integração proxy com [[AWS Lambda|Lambda]], o [[APIs|API]] Gateway envia para a função um evento contendo headers, path, query string, método HTTP, corpo e contexto da requisição.

A função processa e devolve uma resposta no formato esperado.

**HTTP [[APIs|API]] vs REST [[APIs|API]]**

A AWS possui modelos diferentes de [[APIs|APIs]].

Em termos didáticos:

* HTTP [[APIs|APIs]]: mais simples, geralmente mais baratas e com menos recursos avançados.
* REST [[APIs|APIs]]: mais antigas e com mais recursos de controle, validação, [[APIs|API]] keys e cenários complexos.

A escolha depende da necessidade de recursos e do custo.

---

## Exemplo prático

Uma [[APIs|API]] de cadastro usa:

1. `POST /usuarios` no [[APIs|API]] Gateway.
2. Integração com [[AWS Lambda]].
3. [[AWS Lambda|Lambda]] valida entrada.
4. [[AWS Lambda|Lambda]] grava no [[Amazon RDS]].
5. [[AWS Lambda|Lambda]] publica evento no [[Amazon EventBridge]].
6. Logs e métricas vão para [[Amazon CloudWatch]].

[[APIs|API]] Gateway é a porta. [[AWS Lambda|Lambda]] é a execução. [[Amazon RDS|RDS]] é persistência. EventBridge distribui eventos. CloudWatch observa.

---

## Diferenças importantes

**Como Diferenciar**

* Subnet pertence a uma única AZ.
* [[Amazon VPC|VPC]] é regional.
* Internet Gateway permite rota pública.
* NAT Gateway permite saída de subnets privadas.
* Route table decide para onde o pacote vai.

---

## Cuidados

**Segurança**

[[APIs|API]] Gateway pode ser protegido por:

* [[AWS Identity and Access Management (IAM)|IAM]];
* autorizadores [[AWS Lambda|Lambda]];
* tokens JWT;
* [[APIs|API]] keys;
* throttling;
* [[AWS WAF]];
* HTTPS;
* políticas de recurso.

O erro comum é expor uma função sem pensar em autenticação, limites e logs.

Security group não cria rota. Route table não libera porta. Cada componente resolve uma parte diferente da rede.

---

## Relação com outras notas

- [[AWS Lambda]]
- [[Amazon RDS]]
- [[Amazon EventBridge]]
- [[Amazon CloudWatch]]
- [[AWS WAF]]

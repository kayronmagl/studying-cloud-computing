Refatorar é a estratégia de migração em que a aplicação é redesenhada para aproveitar melhor recursos nativos da nuvem.

Também aparece como refactor ou re-architect.


Refatorar é mais profundo do que migrar.

Você não está apenas mudando a aplicação de lugar. Você está mudando como ela funciona.

Exemplo: uma aplicação monolítica pode ser redesenhada com filas, eventos, funções serverless, bancos gerenciados e microsserviços.

---

## Como reconhecer

Procure palavras como:


* alterar arquitetura
* redesenhar aplicação
* usar recursos nativos da nuvem
* cloud-native
* modernizar profundamente


Quando isso aparecer, a resposta tende a ser refatorar.

---

## Diferença para conceitos parecidos

* Rehost: levar como está.
* Replatform: ajustar sem redesenhar completamente.
* Repurchase: trocar por outro produto.
* Refactor: redesenhar para cloud-native.


---

## Exemplo

Antes:


* aplicação monolítica em servidor local
* banco local
* processamento síncrono
* deploy manual


Depois de refatorar:


* API Gateway
* Lambda ou containers
* SQS para desacoplamento
* DynamoDB ou Aurora
* observabilidade com CloudWatch
* deploy automatizado


---

## Cuidado importante

Refatorar pode trazer mais benefício, mas exige mais tempo, mudança e risco.

Por isso, nem toda aplicação deve ser refatorada logo no começo.

---

## Explicação principal

Refatorar é redesenhar a aplicação para tirar proveito da nuvem.

Não é só copiar e colar a aplicação em outro servidor.

---

## Exemplo na prática

Antes:


* aplicação monolítica
* servidor único
* processamento direto
* banco local


Depois de refatorar:


* API gerenciada
* funções ou containers
* fila SQS
* banco gerenciado
* eventos
* monitoramento


---

## Como Diferenciar

Palavras-chave:


* redesenhar
* alterar arquitetura
* recursos nativos da nuvem
* cloud-native


A resposta é Refatorar.

---

## Cuidado importante na prática

Refatorar costuma ser mais poderoso, mas também mais trabalhoso.

Por isso, nem sempre é a primeira escolha em uma migração.

---

## Pensando como professor

Refatorar é quando a empresa aproveita a ida para a nuvem para melhorar profundamente a aplicação.

Ela não pergunta apenas:


* onde vou hospedar isso?


Ela pergunta:


* como eu redesenharia isso se já tivesse nascido para a nuvem?


---

## Exemplo mais concreto

Uma aplicação antiga faz tudo dentro de um único servidor.

Ao refatorar, a equipe pode separar partes da aplicação, usar filas para desacoplar processamento, banco gerenciado para reduzir operação, cache para melhorar performance e funções serverless para tarefas orientadas a eventos.

---

## Resposta curta para guardar

Quando o cenário envolve alterar arquitetura e usar recursos nativos da nuvem, é refatorar.

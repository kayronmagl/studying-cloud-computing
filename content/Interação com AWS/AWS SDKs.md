AWS SDKs são bibliotecas oficiais para linguagens como Python, JavaScript, Java, Go e C#. Elas permitem que aplicações chamem serviços como [[Amazon S3]], [[AWS Lambda]] e [[Amazon DynamoDB]].

AWS SDKs mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## O que é

AWS SDKs são bibliotecas oficiais para aplicações conversarem com serviços AWS usando linguagens de programação.

SDK significa Software Development Kit, ou kit de desenvolvimento de software. Na prática, é um conjunto de bibliotecas, tipos, funções, clientes e utilitários que uma aplicação usa para chamar [[APIs|APIs]] de um serviço sem precisar montar manualmente cada requisição HTTP.

Em vez de uma pessoa digitar comandos, o próprio código chama serviços como [[Amazon S3|S3]], [[Amazon DynamoDB|DynamoDB]], [[Amazon SQS|SQS]] ou [[AWS Lambda|Lambda]].

O ponto central é este: SDK não é um serviço da nuvem. SDK é a ponte usada pelo código da aplicação para conversar com serviços da nuvem.

---

## Por que existe

AWS SDKs existe para explicar uma forma de criar, consultar, alterar ou automatizar recursos em nuvem. Toda interação com AWS passa por [[APIs|APIs]], permissões, auditoria e algum nível de governança.

---

## Como funciona

O funcionamento segue um fluxo simples.

Primeiro, a aplicação cria um cliente do serviço. Esse cliente é um objeto de código configurado para falar com um serviço específico, como [[Amazon S3]], [[Amazon DynamoDB]] ou [[Amazon SQS]].

Depois, o código chama uma operação. Exemplos: enviar um objeto para o [[Amazon S3|S3]], gravar um item no [[Amazon DynamoDB|DynamoDB]], publicar uma mensagem no [[Amazon SQS|SQS]] ou invocar uma função [[AWS Lambda|Lambda]].

Em seguida, o SDK monta a chamada para a [[APIs|API]] da AWS, assina a requisição com credenciais autorizadas, envia a solicitação pela rede e recebe a resposta.

Mesmo usando SDK, a ação continua dependendo de permissões. Se a aplicação não tiver autorização no [[AWS Identity and Access Management (IAM)|IAM]], a chamada falha.

---

## Exemplo prático

Um usuário pode criar um [[Buckets S3|bucket S3]] pelo console. Um script pode criar o mesmo [[Buckets S3|bucket]] pela [[AWS CLI]]. Uma aplicação pode enviar [[Objetos S3|objetos]] usando [[AWS SDKs|SDK]]. Um template de infraestrutura como código pode declarar o [[Buckets S3|bucket]] de forma versionada.

O serviço resultante é o mesmo, mas o método de interação muda.

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em [[Infraestrutura como Código (IaC)|IaC]] para reproduzir ambientes. Aplicações usam SDKs para falar com [[Amazon S3|S3]], [[Amazon DynamoDB|DynamoDB]] ou [[Amazon SQS|SQS]].

Uma aplicação Python pode usar SDK para enviar arquivo ao [[Amazon S3|S3]].

Uma aplicação Node.js pode publicar mensagem no [[Amazon SQS|SQS]].

Um backend Java pode consultar [[Amazon DynamoDB|DynamoDB]].

---

## Diferenças importantes

**Diferença para [[AWS CLI|CLI]]**

A [[AWS CLI|CLI]] é usada por humanos e scripts.

SDKs são usados dentro de aplicações.

Ambos chamam [[APIs|APIs]] da AWS.

**Termos que não devem ficar soltos**

* [[Amazon S3|S3]]: serviço de armazenamento de objetos.
* [[Buckets S3|Bucket S3]]: contêiner lógico onde objetos do S3 ficam armazenados.
* [[Objetos S3|Objeto S3]]: unidade armazenada no S3, como arquivo, imagem, log ou backup.
* [[Amazon DynamoDB|DynamoDB]]: banco NoSQL gerenciado, usado para acesso por chave em baixa latência.
* [[Amazon SQS|SQS]]: serviço de filas para comunicação assíncrona entre componentes.
* [[AWS Lambda|Lambda]]: serviço para executar funções em resposta a eventos sem administrar servidores diretamente.

---

## Cuidados

Operação manual é útil no aprendizado, mas pode gerar inconsistência em produção.

Por isso, conforme o ambiente amadurece, automação, versionamento, permissões bem definidas e auditoria com [[AWS CloudTrail]] tornam-se essenciais.

Toda interação precisa respeitar [[AWS Identity and Access Management (IAM)|IAM]], auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.

SDK não dispensa [[AWS Identity and Access Management (IAM)|IAM]]. A aplicação precisa de credenciais ou role com permissões adequadas. Em [[Amazon EC2|EC2]], usa-se geralmente role de instância; em [[AWS Lambda|Lambda]], role de execução.

---

## Relação com outras notas

- [[Amazon S3]]
- [[AWS Lambda]]
- [[Amazon DynamoDB]]
- [[Amazon SQS]]
- [[Buckets S3]]
- [[Objetos S3]]
- [[AWS CLI]]
- [[APIs]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS CloudTrail]]

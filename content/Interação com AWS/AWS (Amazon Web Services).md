AWS (Amazon Web Services) é o provedor de nuvem da Amazon. Ele oferece computação, armazenamento, bancos, redes, segurança, monitoramento e automação sobre uma [[Infraestrutura Global de Nuvem]].

---

## Visão geral

AWS (Amazon Web Services) mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## Exemplo Prático

Um usuário pode criar um bucket S3 pelo console. Um script pode criar o mesmo bucket pela AWS CLI. Uma aplicação pode enviar objetos usando SDK. Um template de infraestrutura como código pode declarar o bucket de forma versionada.

O serviço resultante é o mesmo, mas o método de interação muda.

---

## Cuidados importantes

Operação manual é útil no aprendizado, mas pode gerar inconsistência em produção.

Por isso, conforme o ambiente amadurece, automação, versionamento, permissões bem definidas e auditoria com [[AWS CloudTrail]] tornam-se essenciais.

---

## Exemplo Arquitetural

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em IaC para reproduzir ambientes. Aplicações usam SDKs para falar com S3, DynamoDB ou SQS.

---

## Cuidado adicional

Toda interação precisa respeitar IAM, auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.

## Como entender isso

A AWS é um provedor de computação em nuvem. Na hora de estudar, a ideia principal é que ela oferece recursos de TI sob demanda, como servidores, armazenamento, bancos, redes, segurança e ferramentas de operação.

A diferença para infraestrutura tradicional é que o cliente não precisa comprar e instalar tudo antes. Ele consome serviços e paga conforme uso.

## O que você precisa saber

* AWS é um provedor, não um único serviço.
* Os serviços ficam distribuídos em regiões, zonas de disponibilidade e pontos de borda.
* A AWS opera a infraestrutura física, mas o cliente ainda configura seus recursos.
* O modelo financeiro é principalmente [[Pay-as-you-go]].
* A segurança segue o [[Modelo de Responsabilidade Compartilhada]].

## Cuidado importante

AWS não significa “a Amazon cuida de tudo”. A AWS cuida da infraestrutura da nuvem; o cliente cuida do que configura dentro dela, como permissões, dados, sistema operacional em EC2, regras de rede e aplicações.

---

## Empresas de nuvem

A AWS é um exemplo de [[Provedores de Nuvem]], junto com outras plataformas que oferecem infraestrutura e serviços sob demanda.

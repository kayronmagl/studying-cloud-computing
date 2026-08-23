AWS (Amazon Web Services) é o provedor de nuvem da Amazon. Ele oferece computação, armazenamento, bancos, redes, segurança, monitoramento e automação sobre uma [[Infraestrutura Global de Nuvem]].

---

## O que é

A AWS é um provedor de computação em nuvem. Na hora de estudar, a ideia principal é que ela oferece recursos de TI sob demanda, como servidores, armazenamento, bancos, redes, segurança e ferramentas de operação.

A diferença para infraestrutura tradicional é que o cliente não precisa comprar e instalar tudo antes. Ele consome serviços e paga conforme uso.

A AWS costuma organizar parte da proposta de valor da nuvem em seis benefícios recorrentes, como troca de despesas fixas por variáveis, elasticidade, velocidade de provisionamento e alcance global. Esses pontos são uma forma de estudar os [[Benefícios da Computação em Nuvem]], mas não são exclusivos da AWS e dependem de arquitetura, governança e operação para se concretizarem.

* AWS é um provedor, não um único serviço.
* Os serviços ficam distribuídos em regiões, zonas de disponibilidade e pontos de borda.
* A AWS opera a infraestrutura física, mas o cliente ainda configura seus recursos.
* O modelo financeiro é principalmente [[Pay-as-you-go]].
* A segurança segue o [[Modelo de Responsabilidade Compartilhada]].

---

## Por que existe

AWS (Amazon Web Services) existe para explicar uma forma de criar, consultar, alterar ou automatizar recursos em nuvem. Toda interação com AWS passa por [[APIs|APIs]], permissões, auditoria e algum nível de governança.

---

## Como funciona

**Origem da AWS**

A AWS surgiu a partir de necessidades internas da Amazon. Conforme a operação de comércio eletrônico cresceu, a empresa precisou lidar com mais servidores, armazenamento, capacidade de computação, redes e processos de provisionamento.

Para reduzir repetição e aumentar escala, equipes internas passaram a criar mecanismos padronizados para operar essa infraestrutura. A percepção técnica foi que parte desses mecanismos poderia ser oferecida a outras organizações como serviços sob demanda, em vez de permanecer apenas como ferramentas internas.

O primeiro serviço público de infraestrutura lançado pela AWS foi o [[Amazon SQS]], voltado a filas de mensagens. Depois vieram serviços que se tornaram centrais na plataforma, como [[Amazon S3]] para armazenamento de objetos e [[Amazon EC2]] para servidores virtuais.

Essa história ajuda a entender a AWS como implementação concreta de [[O que é computação em nuvem]], não como sinônimo de computação em nuvem. O conceito geral é mais amplo; a AWS é um provedor que oferece esse modelo por meio de serviços específicos.

AWS (Amazon Web Services) mostra como você conversa com a AWS. A ideia é simples: tudo que você cria, consulta ou altera precisa passar por alguma interface e por permissões.

Pense nisso como a ponte entre você, seu código e os serviços da AWS.

---

## Exemplo prático

Um usuário pode criar um [[Buckets S3|bucket S3]] pelo console. Um script pode criar o mesmo [[Buckets S3|bucket]] pela [[AWS CLI]]. Uma aplicação pode enviar objetos usando [[AWS SDKs|SDK]]. Um template de infraestrutura como código pode declarar o [[Buckets S3|bucket]] de forma versionada.

O serviço resultante é o mesmo, mas o método de interação muda.

Uma equipe pode criar recursos manualmente no início, mas depois declarar tudo em [[Infraestrutura como Código (IaC)|IaC]] para reproduzir ambientes. Aplicações usam [[AWS SDKs|SDKs]] para falar com [[Amazon S3|S3]], [[Amazon DynamoDB|DynamoDB]] ou [[Amazon SQS|SQS]].

---

## Diferenças importantes

Compare AWS (Amazon Web Services) com console, CLI, SDK, API e IaC. Console favorece exploração visual; CLI favorece terminal e scripts; SDK fica dentro da aplicação; API é a interface base; IaC descreve infraestrutura em arquivos.

---

## Cuidados

Operação manual é útil no aprendizado, mas pode gerar inconsistência em produção.

Por isso, conforme o ambiente amadurece, automação, versionamento, permissões bem definidas e auditoria com [[AWS CloudTrail]] tornam-se essenciais.

Toda interação precisa respeitar [[AWS Identity and Access Management (IAM)|IAM]], auditoria, versionamento e revisão.

Operação manual sem registro dificulta troubleshooting e governança.

AWS não significa “a Amazon cuida de tudo”. A AWS cuida da infraestrutura da nuvem; o cliente cuida do que configura dentro dela, como permissões, dados, sistema operacional em [[Amazon EC2|EC2]], regras de rede e aplicações.

---

## Relação com outras notas

**Empresas de nuvem**

A AWS é um exemplo de [[Provedores de Nuvem]], junto com outras plataformas que oferecem infraestrutura e serviços sob demanda.

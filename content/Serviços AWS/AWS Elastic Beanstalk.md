AWS Elastic Beanstalk é um serviço para implantar, monitorar e escalar aplicações web na AWS com menos trabalho operacional.

Você envia a aplicação, escolhe a plataforma e o Beanstalk provisiona recursos como instâncias [[Amazon EC2|EC2]], balanceamento de carga, monitoramento de integridade e escalabilidade do ambiente.

Elastic Beanstalk fica entre controle e simplicidade.

Ele não é tão manual quanto criar tudo diretamente com [[Amazon EC2|EC2]], load balancer, Auto Scaling e CloudWatch. Também não é o mesmo modelo de [[AWS Lambda|Lambda]], porque normalmente ainda há um ambiente de aplicação rodando sobre recursos provisionados.

---

## O que é

AWS Elastic Beanstalk deve ser entendido como um serviço gerenciado da AWS. Um serviço gerenciado recebe configuração, aplica permissões, registra eventos, gera métricas e cobra conforme uso, capacidade ou recurso associado.

AWS Elastic Beanstalk deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

AWS Elastic Beanstalk existe para resolver uma limitação prática de sistemas: executar, armazenar, conectar, proteger, observar, escalar ou governar recursos.

---

## Como funciona

AWS Elastic Beanstalk funciona por configuração, entrada, processamento, saída, limites, permissões e integração com outros componentes. O valor aparece quando o conceito é ligado a um fluxo real.

---

## Exemplo prático

Uma equipe tem uma aplicação web em Java, Python, Node.js ou outra plataforma compatível. Ela quer publicar rapidamente na AWS sem montar cada componente do zero.

Nesse caso, o Elastic Beanstalk pode criar o ambiente, implantar a aplicação e configurar partes importantes da infraestrutura.

---

## Diferenças importantes

**Quando faz sentido**

Elastic Beanstalk faz sentido quando a equipe quer publicar uma aplicação web com menos trabalho de infraestrutura.

Ele é útil para aprender deploy na AWS sem montar manualmente todos os componentes desde o começo. Ainda assim, é importante lembrar que recursos reais são criados por trás, como [[Amazon EC2|EC2]], balanceamento de carga, Auto Scaling e monitoramento.

**Diferença para criar tudo manualmente**

Sem Elastic Beanstalk, a equipe pode precisar configurar manualmente instâncias [[Amazon EC2|EC2]], balanceador de carga, Auto Scaling, monitoramento, ambiente de execução e deploy.

Com Elastic Beanstalk, parte dessa estrutura é criada e coordenada pelo serviço. A aplicação ainda roda em recursos reais da AWS, mas a experiência fica mais simples para quem quer publicar e escalar uma aplicação web sem montar cada peça separadamente.

Isso não significa perder toda flexibilidade. O Beanstalk permite ajustar configurações, mas o objetivo principal é reduzir trabalho operacional inicial.

---

## Cuidados

O cuidado principal em AWS Elastic Beanstalk é usar o termo fora de contexto. Verifique função, dependências, custo, segurança, limite e impacto operacional.

---

## Relação com outras notas

- [[O que é computação em nuvem]]

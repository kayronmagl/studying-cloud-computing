AWS Fargate é um mecanismo de computação serverless para containers.

Ele funciona com [[Amazon ECS]] e [[Amazon EKS]], permitindo executar containers sem provisionar, configurar ou escalar clusters de instâncias [[Amazon EC2]]. A equipe define imagem, CPU, memória, rede, variáveis e permissões; a AWS gerencia a infraestrutura subjacente.

---

## Visão geral

AWS Fargate faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## Problema que Resolve

Containers resolvem empacotamento de aplicação, mas não eliminam a necessidade de infraestrutura.

Sem Fargate, uma equipe pode precisar manter nós EC2 para executar containers, dimensionar cluster, atualizar instâncias, otimizar bin packing e cuidar de capacidade.

Com Fargate, o foco fica na tarefa ou pod, não no servidor que executa o container.

---

## Relação com Lambda

[[AWS Lambda]] executa funções.

Fargate executa containers.

Lambda é melhor para funções curtas, orientadas a eventos e com limites claros de execução. Fargate é melhor quando a aplicação já está empacotada como container, precisa de servidor HTTP contínuo, runtime específico ou controle maior sobre processo e dependências.

---

## Exemplo

Uma API Node.js containerizada pode rodar no [[Amazon ECS]] com Fargate.

A equipe define:

* imagem Docker;
* CPU e memória;
* porta;
* variáveis de ambiente;
* [[Amazon VPC]];
* [[Security Groups]];
* permissões IAM;
* logs no [[Amazon CloudWatch]].

A AWS executa a tarefa sem que a equipe gerencie instâncias EC2.

---

## Cuidados importantes

Fargate reduz operação de servidores, mas ainda exige arquitetura de rede, observabilidade, controle de custos, políticas IAM, health checks, autoscaling e estratégia de deploy.

---

## Exemplo Prático

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige IAM, logs, retries, DLQ e idempotência.

---

## Cuidado adicional

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.

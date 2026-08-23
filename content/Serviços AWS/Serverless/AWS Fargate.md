AWS Fargate é um mecanismo de computação serverless para containers.

Ele funciona com [[Amazon ECS]] e [[Amazon EKS]], permitindo executar containers sem provisionar, configurar ou escalar clusters de instâncias [[Amazon EC2]]. A equipe define imagem, CPU, memória, rede, variáveis e permissões; a AWS gerencia a infraestrutura subjacente.

AWS Fargate faz parte do modelo em que você foca mais no código, evento e integração, e menos no servidor. Mas serverless não é mágica: ainda há limites, permissões, logs, custo e falhas.

Leia pensando no fluxo de eventos.

---

## O que é

AWS Fargate deve ser entendido como execução ou integração sem administração direta de servidores. Os servidores continuam existindo, mas a equipe trabalha mais perto de eventos, funções, limites e configuração do serviço.

---

## Por que existe

Containers resolvem empacotamento de aplicação, mas não eliminam a necessidade de infraestrutura.

Sem Fargate, uma equipe pode precisar manter nós [[Amazon EC2|EC2]] para executar containers, dimensionar cluster, atualizar instâncias, otimizar bin packing e cuidar de capacidade.

Com Fargate, o foco fica na tarefa ou pod, não no servidor que executa o container.

---

## Como funciona

O funcionamento normalmente envolve eventos, funções, integrações gerenciadas, permissões e execução sob demanda. Ao estudar AWS Fargate, acompanhe o evento de entrada, a execução, o estado, a falha e o registro gerado.

---

## Exemplo prático

Uma [[APIs|API]] Node.js containerizada pode rodar no [[Amazon ECS]] com Fargate.

A equipe define:

* imagem Docker;
* CPU e memória;
* porta;
* variáveis de ambiente;
* [[Amazon VPC]];
* [[Security Groups]];
* permissões [[AWS Identity and Access Management (IAM)|IAM]];
* logs no [[Amazon CloudWatch]].

A AWS executa a tarefa sem que a equipe gerencie instâncias [[Amazon EC2|EC2]].

Um upload no [[Amazon S3]] pode acionar uma função [[AWS Lambda]], que processa o arquivo, publica evento no [[Amazon EventBridge]] e envia mensagem para [[Amazon SQS]] em caso de processamento posterior.

Esse fluxo não exige gerenciar servidor, mas exige [[AWS Identity and Access Management (IAM)|IAM]], logs, retries, DLQ e idempotência.

---

## Diferenças importantes

Não confunda serverless com ausência de infraestrutura. Servidores continuam existindo, mas a administração direta de capacidade, provisionamento e parte da operação fica com o provedor.

---

## Cuidados

Fargate reduz operação de servidores, mas ainda exige arquitetura de rede, observabilidade, controle de custos, políticas [[AWS Identity and Access Management (IAM)|IAM]], health checks, autoscaling e estratégia de deploy.

Serverless não elimina arquitetura.

Limites de execução, cold start, concorrência, permissões, custo por invocação e falhas assíncronas precisam ser tratados de forma explícita.

---

## Relação com outras notas

**Relação com [[AWS Lambda|Lambda]]**

[[AWS Lambda]] executa funções.

Fargate executa containers.

[[AWS Lambda|Lambda]] é melhor para funções curtas, orientadas a eventos e com limites claros de execução. Fargate é melhor quando a aplicação já está empacotada como container, precisa de servidor HTTP contínuo, runtime específico ou controle maior sobre processo e dependências.

Amazon ECS orquestra containers na AWS. Ele executa tarefas e serviços usando [[Amazon EC2|EC2]] ou Fargate como capacidade de execução.

---

## O que é

Amazon ECS deve ser entendido como um serviço gerenciado da AWS. Um serviço gerenciado recebe configuração, aplica permissões, registra eventos, gera métricas e cobra conforme uso, capacidade ou recurso associado.

Amazon ECS deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

Amazon ECS existe para resolver uma limitação prática de sistemas: executar, armazenar, conectar, proteger, observar, escalar ou governar recursos.

---

## Como funciona

Amazon ECS funciona por configuração, entrada, processamento, saída, limites, permissões e integração com outros componentes. O valor aparece quando o conceito é ligado a um fluxo real.

---

## Exemplo prático

Uma aplicação em containers pode ser dividida em serviços menores, cada um rodando sua própria imagem.

O ECS ajuda a executar esses containers, manter a quantidade desejada de tarefas, reiniciar o que falha e integrar com balanceadores de carga e outros serviços da AWS.

Ele é uma boa opção quando a equipe quer containers na AWS, mas não precisa ou não quer operar Kubernetes diretamente.

---

## Diferenças importantes

**Quando faz sentido**

ECS faz sentido quando a equipe quer executar containers na AWS sem adotar diretamente Kubernetes.

Ele pode usar [[Amazon EC2|EC2]] como capacidade por trás ou Fargate para evitar a administração de servidores. Essa flexibilidade faz do ECS uma opção comum para aplicações em containers que precisam escalar e integrar com serviços AWS.

---

## Cuidados

O cuidado principal em Amazon ECS é usar o termo fora de contexto. Verifique função, dependências, custo, segurança, limite e impacto operacional.

---

## Relação com outras notas

**Relação com AWS Fargate**

Este serviço pode ser combinado com [[AWS Fargate]] quando a equipe quer executar containers sem administrar diretamente instâncias [[Amazon EC2]] como capacidade do cluster.

Com Fargate, o foco operacional muda: em vez de manter servidores para containers, a equipe define CPU, memória, imagem, rede, permissões e políticas de execução. A AWS assume a camada de infraestrutura subjacente.

Esse modelo se encaixa em [[Computação sem Servidor (Serverless)]] porque reduz o gerenciamento de servidores, embora a aplicação continue empacotada como container.

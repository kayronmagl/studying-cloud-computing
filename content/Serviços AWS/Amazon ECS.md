Amazon ECS orquestra containers na AWS. Ele executa tarefas e serviços usando EC2 ou Fargate como capacidade de execução.

## Relação com AWS Fargate

Este serviço pode ser combinado com [[AWS Fargate]] quando a equipe quer executar containers sem administrar diretamente instâncias [[Amazon EC2]] como capacidade do cluster.

Com Fargate, o foco operacional muda: em vez de manter servidores para containers, a equipe define CPU, memória, imagem, rede, permissões e políticas de execução. A AWS assume a camada de infraestrutura subjacente.

Esse modelo se encaixa em [[Computação sem Servidor (Serverless)]] porque reduz o gerenciamento de servidores, embora a aplicação continue empacotada como container.

## Quando faz sentido

ECS faz sentido quando a equipe quer executar containers na AWS sem adotar diretamente Kubernetes.

Ele pode usar EC2 como capacidade por trás ou Fargate para evitar a administração de servidores. Essa flexibilidade faz do ECS uma opção comum para aplicações em containers que precisam escalar e integrar com serviços AWS.

---

## Exemplo aplicado

Uma aplicação em containers pode ser dividida em serviços menores, cada um rodando sua própria imagem.

O ECS ajuda a executar esses containers, manter a quantidade desejada de tarefas, reiniciar o que falha e integrar com balanceadores de carga e outros serviços da AWS.

Ele é uma boa opção quando a equipe quer containers na AWS, mas não precisa ou não quer operar Kubernetes diretamente.

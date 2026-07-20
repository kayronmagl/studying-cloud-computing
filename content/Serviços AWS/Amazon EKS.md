Amazon EKS é o serviço gerenciado da AWS para executar Kubernetes.

Kubernetes é uma plataforma usada para orquestrar aplicações em containers. O EKS reduz o trabalho de operar o plano de controle do Kubernetes e integra o cluster com serviços da AWS.

---

## Visão geral

Use EKS quando a aplicação já usa Kubernetes ou quando a equipe precisa do ecossistema Kubernetes para organizar containers, escalar aplicações, controlar deploys e integrar componentes.

O EKS não é um banco de dados, não é machine learning e não é data warehouse. Ele pertence ao assunto de containers.

---

## Diferença para serviços parecidos

| Serviço | Ideia principal |
|---|---|
| Amazon ECS | Orquestração de containers própria da AWS |
| Amazon EKS | Kubernetes gerenciado |
| AWS Fargate | Execução de containers sem gerenciar servidores |
| AWS Lambda | Execução de funções orientadas a eventos |

---

## Como Diferenciar

Quando o cenário envolve em Kubernetes ou aplicações em containers na AWS, [[Amazon EKS]] quando a alternativa mencionar Kubernetes gerenciado costuma ser a associação mais direta.

---

## Quando faz sentido

EKS faz sentido quando Kubernetes já faz parte da estratégia da equipe.

Ele não é a opção mais simples para todo projeto. Para uma aplicação pequena, talvez Elastic Beanstalk, ECS, Fargate ou Lambda sejam mais diretos. O valor do EKS aparece quando a equipe precisa do modelo Kubernetes, de portabilidade, de add-ons do ecossistema ou de controle mais rico sobre workloads em containers.

---

## Exemplo aplicado

Imagine uma empresa que já usa Kubernetes fora da AWS.

Ela tem manifests, pipelines, equipes treinadas, políticas e ferramentas em torno de Kubernetes. Ao migrar para AWS, abandonar tudo isso talvez não faça sentido. O Amazon EKS permite continuar usando Kubernetes, mas com plano de controle gerenciado pela AWS.

Isso reduz parte da operação mais pesada, embora a equipe ainda precise entender nós, pods, serviços, redes, permissões e atualizações do cluster.

---

## Cuidado importante

EKS não elimina a necessidade de entender Kubernetes.

A AWS gerencia partes importantes do serviço, mas a equipe ainda precisa compreender pods, deployments, services, nodes, permissões, redes e atualizações.

Se a equipe quer apenas executar containers com menos complexidade, [[Amazon ECS]] ou [[AWS Fargate]] podem ser alternativas mais simples.

---

## Quando não escolher EKS

EKS pode ser poderoso, mas também traz complexidade.

Se a equipe não precisa de Kubernetes, talvez a escolha mais simples seja ECS, Fargate, Elastic Beanstalk ou Lambda. A melhor decisão depende do nível de controle necessário, da experiência da equipe e do tipo de aplicação.

A associação mais comum é EKS a Kubernetes. Em arquitetura real, avalie se Kubernetes é realmente necessário.

---

## Exemplo de decisão

Se uma empresa já usa Kubernetes, EKS pode ser uma continuação natural na AWS. Se a equipe ainda não tem experiência com Kubernetes, talvez ECS, Fargate ou Elastic Beanstalk sejam caminhos mais simples. O ponto é não escolher EKS só porque é avançado; ele faz sentido quando Kubernetes realmente resolve o problema.

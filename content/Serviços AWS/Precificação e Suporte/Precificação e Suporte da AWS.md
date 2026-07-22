Precificação e Suporte da AWS é o módulo que conecta tecnologia, custo, governança financeira e operação assistida.

Depois que uma arquitetura usa computação, armazenamento, bancos, redes, segurança, escala e mensageria, surge uma pergunta inevitável:


* quanto isso custa, como controlar e como obter ajuda quando algo falha?


Esse módulo responde essa pergunta.


Precificação e Suporte da AWS mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Por que é um Módulo Próprio

Precificação e suporte não devem ficar perdidos dentro de serviços individuais.

Eles atravessam toda a arquitetura.

Uma decisão em [[Amazon EC2]] afeta custo de computação. Uma decisão em [[Amazon S3]] afeta armazenamento, requisições e transferência. Uma decisão em [[Amazon VPC]] pode gerar custo de NAT Gateway ou tráfego. Uma decisão em [[Amazon CloudWatch]] pode gerar custo de logs e métricas.

---

## Eixos

O módulo possui dois eixos:

* custo e cobrança;
* suporte e operação.

No eixo de custo, entram [[AWS Pricing Calculator]], [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Savings Plans]], [[Reserved Instances]], [[Spot Instances]], tags e FinOps.

No eixo de suporte, entram [[AWS Support]], [[Planos do AWS Support]], [[AWS Trusted Advisor]], [[AWS Health Dashboard]], [[Service Quotas]] e abertura de [[Support Case]].

---

## Ideia Central

Nuvem troca compra antecipada de infraestrutura por consumo contínuo.

Isso aumenta flexibilidade, mas exige disciplina.

Sem governança, a elasticidade que ajuda a escalar também pode aumentar custo rapidamente.
---

## Conceitos de Fechamento

Para fechar o estudo de custo e operação, alguns conceitos conectam estratégia, suporte e governança:

* [[Custo Total de Propriedade (TCO)]], para comparar nuvem com infraestrutura tradicional;
* [[AWS Well-Architected Tool]], para aplicar o [[AWS Well-Architected Framework]] em revisões práticas;
* [[AWS rePost]], como apoio de comunidade e conhecimento;
* [[Escalation Management]], para tratar incidentes e problemas críticos de suporte.

Esses conceitos mostram que custo e suporte não são apenas fatura e chamado. Eles fazem parte da maturidade operacional.
---

## Gestão Financeira da Nuvem

O conteúdo de [[Gestão Financeira da Nuvem]] fica em uma pasta própria dentro deste módulo porque ele aprofunda a operação econômica da nuvem.

Esse eixo organiza o estudo em cinco capacidades:

* [[Acessar Custos da AWS]];
* [[Organizar Custos da AWS]];
* [[Compreender Custos da AWS]];
* [[Controlar Custos da AWS]];
* [[Otimizar Custos da AWS]].

Essas capacidades conectam ferramentas como [[AWS Billing Dashboard]], [[Página de Faturas da AWS]], [[AWS Cost Explorer]], [[AWS Cost and Usage Report (CUR)]], [[Cost Allocation Tags]], [[AWS Cost Categories]], [[AWS Budgets]], [[AWS Compute Optimizer]], [[AWS Instance Scheduler]], [[AWS Organizations]], [[AWS Control Tower]] e [[AWS Service Catalog]].

## Como entender isso

Este conceito pertence à camada de precificação, suporte e gestão financeira.

## Ponto central

Na AWS, custo depende de uso, região, serviço, armazenamento, requisições, tráfego, logs, suporte e compromissos de uso.

## Como Diferenciar

* Pricing Calculator estima custo antes.
* Cost Explorer analisa custo real.
* Budgets alerta sobre limites.
* Tags ajudam alocação de custo.
* Trusted Advisor recomenda melhorias.
* Support Plans mudam nível de suporte.

## Cuidado importante

Pay-as-you-go não significa barato. Significa pagar conforme uso. Uso sem controle pode ficar caro.

---

## Conceitos que completam o assunto

O custo final também depende do [[AWS Free Tier]], do [[Custo de Transferência de Dados]], dos [[Custos por Região]] e de controles como [[Alarmes de Faturamento com Amazon CloudWatch]]. Esses pontos explicam por que duas arquiteturas parecidas podem gerar faturas diferentes.

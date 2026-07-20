AWS Cost Anomaly Detection é o recurso da AWS para detectar anomalias de custo automaticamente.

Ele monitora padrões de gasto e alerta quando identifica comportamento incomum.

---

## Visão geral

AWS Cost Anomaly Detection mostra que nuvem também é decisão financeira. O custo não aparece só porque um serviço existe; ele aparece pelo modo como você usa, escala, transfere, armazena e monitora.


---

## Problema que Resolve

Custos inesperados podem surgir por:

* recurso criado por engano;
* tráfego anormal;
* loop de aplicação;
* ataque;
* logs excessivos;
* aumento de uso;
* configuração errada;
* mudança de preço ou arquitetura.

---

## Como Ajuda

Em vez de esperar fechar a fatura, anomalias podem ser detectadas mais cedo.

Isso reduz impacto financeiro.

---

## Relação com Budgets

[[AWS Budgets]] monitora limites definidos.

Cost Anomaly Detection procura comportamento incomum.

Eles são complementares.

---

## Cuidado

Nem toda anomalia é erro.

Uma campanha real ou pico legítimo pode aumentar custo. A equipe precisa investigar contexto.

---

## Exemplo Prático

Uma arquitetura pode parecer barata no desenho inicial, mas gerar custo por logs excessivos, transferência de dados, NAT Gateway, snapshots antigos, recursos ociosos ou falta de tags.

Ferramentas como [[AWS Cost Explorer]], [[AWS Budgets]], [[AWS Billing and Cost Management]] e [[AWS Trusted Advisor]] ajudam a enxergar e corrigir esses problemas.

---

## Cuidados importantes

Otimizar custo não significa cortar recursos cegamente.

A decisão precisa considerar disponibilidade, segurança, performance, previsibilidade e valor de negócio.

---

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

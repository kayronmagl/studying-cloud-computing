EC2 Instance Savings Plans é uma opção de preço do Amazon EC2 que oferece desconto em troca de um compromisso de gasto por hora.

Você assume esse compromisso por 1 ou 3 anos, ligado a uma família de instância em uma região.


Pense nisso como um acordo financeiro.

Se você sabe que vai usar EC2 continuamente, pode se comprometer a gastar um valor por hora. Em troca, paga menos do que pagaria em On-Demand.

---

## Exemplo simples

Uma empresa sabe que sempre terá aplicações rodando em instâncias da família `m` em uma região.

Em vez de pagar preço On-Demand o tempo todo, ela usa EC2 Instance Savings Plans para reduzir custo.

---

## Como isso aparece em perguntas

A pista costuma ser:


* compromisso de gasto por hora
* família de instância
* região
* 1 ou 3 anos


A resposta é EC2 Instance Savings Plans.

---

## Comparação com outras opções

* On-Demand: paga conforme usa, sem compromisso.
* [[Reserved Instances]]: desconto por reserva/compromisso mais específico.
* EC2 Instance Savings Plans: desconto por compromisso de gasto por hora.
* [[Spot Instances]]: preço variável e risco de interrupção.


---

## Cuidado importante

Muita gente marca Reserved Instances porque também envolve compromisso.

Mas quando a frase fala claramente em compromisso de gasto por hora, a resposta tende a ser Savings Plans.

---

## Exemplo aplicado

Imagine que uma empresa usa EC2 todos os dias para rodar sistemas internos.

Ela já sabe que esse uso não vai desaparecer nos próximos meses.

Nesse caso, pagar tudo como On-Demand pode sair mais caro. Ao assumir um compromisso de gasto por hora, ela recebe desconto.

Essa é a lógica do Savings Plans: a AWS dá desconto porque você assumiu um compromisso previsível.

---

## Decisão de custo

* Qual opção reduz custo quando há compromisso de gasto por hora com família de instância e região por 1 ou 3 anos?


A resposta é EC2 Instance Savings Plans.

Quando o cenário envolve capacidade ociosa e preço por oferta/demanda, aí é Spot.

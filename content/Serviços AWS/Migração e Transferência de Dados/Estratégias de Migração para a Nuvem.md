Estratégias de Migração para a Nuvem são formas de mover, manter, substituir ou transformar aplicações durante uma jornada para cloud.

Em materiais AWS, esse assunto costuma aparecer como os 7 Rs.


Nem toda aplicação deve ir para a nuvem do mesmo jeito.

Às vezes a empresa só quer tirar servidores do datacenter rapidamente. Às vezes quer modernizar. Às vezes percebe que uma aplicação nem precisa mais existir.

Por isso, a estratégia de migração depende de prazo, custo, risco, valor e esforço.

---

## Os 7 Rs

* Rehost: mover como está, lift-and-shift.
* Replatform: fazer pequenos ajustes sem redesenhar tudo.
* Repurchase: trocar por outro produto, geralmente SaaS.
* Refactor / Re-architect: redesenhar a aplicação usando recursos nativos da nuvem.
* Retire: descontinuar aplicação que não precisa mais existir.
* Retain: manter como está por enquanto.
* Relocate: mover workload sem redesenhar, comum em cenários específicos.


---

## Quando cada uma aparece

* Pressa para sair do datacenter: rehost.
* Pequena melhoria sem redesenhar tudo: replatform.
* Trocar aplicação por SaaS: repurchase.
* Modernizar profundamente: refactor.
* Sistema sem valor: retire.
* Sistema que ainda não deve migrar: retain.

---

## Pontos que Costumam Gerar Confusão

Uma pergunta que dizia:


* Qual estratégia envolve alterar a forma como uma aplicação é arquitetada e desenvolvida, normalmente usando recursos nativos da nuvem?


A resposta é [[Refatorar]].

---

## Cuidado importante

* Rehost: muda onde a aplicação roda.
* Replatform: faz ajuste moderado.
* Refactor: muda a arquitetura.


Se a frase fala em arquitetar e desenvolver de novo usando recursos nativos da nuvem, a resposta é refatorar.

---

## Explicação principal

Migrar para a nuvem não significa sempre fazer a mesma coisa.

Às vezes a empresa só move a aplicação. Às vezes melhora um pouco. Às vezes troca por um produto pronto. Às vezes redesenha tudo.

Essas escolhas são as estratégias de migração.

---

## Exemplo com os 7 Rs

* Rehost: levar como está.
* Replatform: mudar um pouco a plataforma.
* Repurchase: trocar por SaaS ou outro produto.
* Refactor: redesenhar para cloud-native.
* Retire: desligar o que não precisa mais.
* Retain: manter como está por enquanto.
* Relocate: mover workload de forma específica, sem redesenhar.


---

## Como Diferenciar

Considere um cenário em que:


* alterar a forma como a aplicação é arquitetada e desenvolvida
* usar recursos nativos da nuvem


a resposta é [[Refatorar]].

---

## Cuidado importante na prática

Rehost é mudança de lugar.

Refatorar é mudança de arquitetura.

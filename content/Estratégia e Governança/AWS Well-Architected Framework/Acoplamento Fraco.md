Acoplamento Fraco é um princípio arquitetural em que componentes dependem o mínimo possível uns dos outros.

Isso melhora resiliência, escalabilidade e facilidade de mudança.

---

## Visão geral

Imagine dois sistemas conectados diretamente.

Se um fica lento, o outro trava. Se um cai, o outro falha junto.

Com acoplamento fraco, você coloca uma camada intermediária, como fila, evento ou API estável.

Assim, cada parte pode evoluir, escalar e falhar com menos impacto na outra.

---

## Pontos que Costumam Gerar Confusão

O cenário descreve qual princípio afirma que sistemas devem reduzir interdependências.

A resposta é Acoplamento fraco.

---

## Exemplos na AWS

* [[Amazon SQS]] entre produtor e consumidor;
* [[Amazon SNS]] para pub/sub;
* [[Amazon EventBridge]] para eventos;
* APIs entre serviços;
* filas para absorver picos;
* DLQ para falhas;
* retries com backoff.

---

## Cuidado importante

Acoplamento fraco não significa ausência de comunicação.

Significa comunicação com menos dependência rígida.

---

## Ideia Central

* se um componente não precisa saber demais sobre o outro, o sistema fica mais flexível


---

## Explicação principal

Acoplamento fraco é fazer com que uma parte do sistema não dependa demais da outra.

Quanto mais grudados os componentes estão, mais fácil uma falha se espalhar.

---

## Exemplo

Sem fila:


* sistema A chama sistema B diretamente
* B fica lento
* A também fica lento


Com fila:


* sistema A envia mensagem para SQS
* sistema B processa quando puder
* A não fica preso esperando


---

## Como Diferenciar

A frase principal é:


* reduzir interdependências


A resposta é Acoplamento fraco.

---

## Serviços que ajudam

* [[Amazon SQS]];
* [[Amazon SNS]];
* [[Amazon EventBridge]];
* [[Dead Letter Queue (DLQ)]];
* retries;
* arquitetura orientada a eventos.

---

## Pensando como arquiteto

Acoplamento fraco é um dos conceitos mais importantes para sistemas modernos.

Quando os componentes são muito dependentes, qualquer atraso ou falha vira efeito dominó.

Com acoplamento fraco, cada parte consegue trabalhar com mais independência.

---

## Exemplo bem simples

Imagine uma loja online.

Quando o cliente finaliza um pedido, o sistema não precisa gerar nota, atualizar estoque, mandar e-mail e processar logística tudo ao mesmo tempo e de forma direta.

Ele pode registrar o pedido e colocar mensagens em uma fila.

Outros componentes processam depois.

Isso deixa o sistema mais resistente.

---

## Resposta curta para guardar

Quando o cenário envolve reduzir interdependências, a resposta é acoplamento fraco.

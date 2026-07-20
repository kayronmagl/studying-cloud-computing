Instâncias Spot são instâncias EC2 que usam capacidade ociosa da AWS com preço variável.

Elas podem ser bem mais baratas, mas têm uma condição importante: podem ser interrompidas quando a AWS precisa da capacidade de volta.

---

## Visão geral

Spot é para trabalho flexível.

Você aceita risco de interrupção para pagar menos.

Isso funciona bem quando a tarefa pode parar e continuar depois, ou quando várias máquinas podem processar partes independentes de um trabalho.

---

## Exemplo simples

Imagine um processamento de imagens com milhares de arquivos.

Se uma instância Spot for interrompida, outra pode continuar o trabalho depois. Como a tarefa tolera interrupção, Spot pode economizar bastante.

---

## Bons usos

* processamento em lote;
* renderização;
* análise de dados;
* testes;
* workers stateless;
* jobs que salvam progresso;
* tarefas que podem ser reiniciadas.

---

## Quando evitar

Evite Spot para banco de dados primário, sistema crítico sem tolerância a interrupção ou aplicação que não sabe lidar com falhas repentinas.

---

## Como isso aparece em perguntas

A pista costuma ser:


* preço ajustado com base na oferta e demanda


A resposta é Instâncias Spot.

---

## Cuidado importante

Spot não é apenas “instância barata”.

Spot é capacidade ociosa com preço variável e possibilidade de interrupção.

---

## Exemplo aplicado

Spot é uma boa opção quando perder uma máquina no meio do processo não destrói o trabalho.

Por exemplo: converter vídeos, processar imagens, rodar simulações, executar testes ou processar partes de um grande lote.

Se uma instância for interrompida, a aplicação precisa conseguir continuar depois.

---

## Pergunta que esta nota responde

* Qual modelo de preço muda conforme oferta e demanda de instâncias EC2?


A resposta é Instâncias Spot.

A palavra “demanda” na pergunta é uma pista forte.

---

## Cuidado de professor

Nunca pense em Spot como primeira escolha para algo que precisa ficar ligado o tempo todo sem interrupção.

Ela é econômica, mas exige tolerância a falhas.

---

## Outra forma de entender

Spot é uma troca: você ganha preço melhor, mas entrega previsibilidade.

Por isso, antes de usar Spot, pergunte:


* se essa instância parar agora, eu perco algo importante?


Se a resposta for “não, o trabalho pode continuar depois”, Spot pode fazer sentido.

Se a resposta for “sim, o sistema para e causa prejuízo”, Spot provavelmente não é a melhor escolha.

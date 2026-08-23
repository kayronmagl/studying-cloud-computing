Amazon Augmented AI, também chamado de Amazon A2I, adiciona revisão humana a previsões de machine learning.

Ele é útil quando um resultado automático tem baixa confiança, envolve uma decisão sensível ou precisa passar por amostragem de qualidade antes de ser aceito.

---

## O que é

Amazon Augmented AI deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

**Situação Atual**

A partir de 30 de julho de 2026, AWS A2I deixará de aceitar novos clientes. Clientes existentes poderão continuar usando o serviço, mas a AWS informou que não planeja introduzir novos recursos.

Por isso, novos projetos devem avaliar cuidadosamente a dependência do serviço e considerar fluxos personalizados de human-in-the-loop quando necessário.

---

## Como funciona

A aplicação define um fluxo de revisão humana e as condições que iniciam uma human loop. Essas condições podem usar limites de confiança, amostragem aleatória ou regras próprias da aplicação.

Quando a revisão é acionada, uma tarefa é enviada a uma força de trabalho humana. O resultado revisado é armazenado e devolvido ao fluxo da aplicação.

A2I possui integrações com Amazon Textract e Amazon Rekognition, além de permitir tarefas personalizadas.

**Componentes**

* tipo de tarefa;
* fluxo de revisão humana;
* modelo de interface da tarefa;
* força de trabalho;
* human loops;
* dados de entrada e saída no [[Amazon S3]];
* permissões do [[AWS Identity and Access Management (IAM)|IAM]].

---

## Exemplo prático

Um sistema extrai dados de documentos. Resultados com alta confiança seguem automaticamente; campos ambíguos são enviados a uma pessoa. Depois da revisão, a aplicação continua o processamento com o valor confirmado.

---

## Diferenças importantes

Compare Amazon Augmented AI com conceitos próximos observando função, camada, limite e responsabilidade. Termos parecidos podem resolver problemas diferentes.

---

## Cuidados

O cuidado principal em Amazon Augmented AI é usar o termo fora de contexto. Verifique função, dependências, custo, segurança, limite e impacto operacional.

---

## Relação com outras notas

- [[O que é computação em nuvem]]

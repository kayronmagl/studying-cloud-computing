Amazon Augmented AI, também chamado de Amazon A2I, adiciona revisão humana a previsões de machine learning.

Ele é útil quando um resultado automático tem baixa confiança, envolve uma decisão sensível ou precisa passar por amostragem de qualidade antes de ser aceito.

---

## Como Funciona

A aplicação define um fluxo de revisão humana e as condições que iniciam uma human loop. Essas condições podem usar limites de confiança, amostragem aleatória ou regras próprias da aplicação.

Quando a revisão é acionada, uma tarefa é enviada a uma força de trabalho humana. O resultado revisado é armazenado e devolvido ao fluxo da aplicação.

A2I possui integrações com Amazon Textract e Amazon Rekognition, além de permitir tarefas personalizadas.

---

## Componentes

* tipo de tarefa;
* fluxo de revisão humana;
* modelo de interface da tarefa;
* força de trabalho;
* human loops;
* dados de entrada e saída no Amazon S3;
* permissões do IAM.

---

## Situação Atual

A partir de 30 de julho de 2026, AWS A2I deixará de aceitar novos clientes. Clientes existentes poderão continuar usando o serviço, mas a AWS informou que não planeja introduzir novos recursos.

Por isso, novos projetos devem avaliar cuidadosamente a dependência do serviço e considerar fluxos personalizados de human-in-the-loop quando necessário.

---

## Exemplo

Um sistema extrai dados de documentos. Resultados com alta confiança seguem automaticamente; campos ambíguos são enviados a uma pessoa. Depois da revisão, a aplicação continua o processamento com o valor confirmado.

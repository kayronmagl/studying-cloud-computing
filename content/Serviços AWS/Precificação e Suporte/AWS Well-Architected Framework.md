AWS Well-Architected Framework é o framework da AWS para avaliar e melhorar workloads na nuvem.

Ele ajuda a revisar decisões de arquitetura com base em pilares de boas práticas.


O Well-Architected olha para uma workload específica: uma aplicação, sistema ou conjunto de componentes que entrega valor para o negócio.

A pergunta central é: esta arquitetura está bem desenhada para operar, proteger dados, resistir a falhas, entregar desempenho, controlar custos e considerar sustentabilidade?

Os seis pilares são Excelência Operacional, Segurança, Confiabilidade, [[Eficiência de Desempenho]], Otimização de Custos e Sustentabilidade.

---

## Diferença para AWS CAF

O [[AWS Cloud Adoption Framework (AWS CAF)]] olha a adoção da nuvem pela organização.

O Well-Architected olha a qualidade de uma workload.

Essa diferença evita confundir transformação organizacional com revisão técnica de uma workload.

---

## Como Diferenciar


Se o foco for transformação organizacional, perspectivas e prontidão para nuvem, pense em AWS CAF.

---

## Exemplo aplicado

Imagine uma aplicação já rodando na AWS.

Ela funciona, mas a equipe não sabe se está segura, resiliente, eficiente, barata de operar ou preparada para falhas. Uma revisão Well-Architected ajuda a fazer essas perguntas de forma organizada.

O resultado não é apenas uma nota. É uma lista de riscos, decisões e melhorias possíveis para aquela workload.

---

## Exemplo de leitura correta

Se uma aplicação tem custo alto, falhas frequentes e pouca visibilidade operacional, o Well-Architected não aponta apenas um serviço mágico.

Ele ajuda a revisar decisões: como a aplicação é monitorada, como falha, como protege dados, como escala, como usa recursos e como controla custos.

Por isso, ele deve ser entendido como um método de avaliação de arquitetura, não como ferramenta isolada de cobrança ou suporte.

---

## Como isso ajuda na prática

Uma revisão Well-Architected ajuda a transformar impressões soltas em decisões objetivas.

Em vez de apenas dizer “a aplicação parece boa”, a equipe verifica riscos, prioriza melhorias e entende quais decisões afetam operação, segurança, confiabilidade, desempenho, custo e sustentabilidade.

Essa abordagem é útil porque uma arquitetura pode funcionar hoje e ainda assim ter riscos escondidos que só aparecem em incidentes, aumento de tráfego ou crescimento da fatura.

---

## Exemplo de aplicação

Uma revisão Well-Architected pode revelar riscos antes que eles virem incidentes. Por exemplo, uma aplicação pode depender de uma única zona de disponibilidade, não ter alarmes úteis, armazenar segredo de forma insegura ou gastar muito por usar recursos maiores que o necessário. O framework ajuda a transformar esses pontos em melhorias priorizadas.

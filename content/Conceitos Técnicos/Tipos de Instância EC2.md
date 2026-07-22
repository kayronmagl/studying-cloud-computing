Tipos de instância EC2 definem a capacidade de uma instância do [[Amazon EC2]].

Eles determinam características como vCPU, memória, desempenho de rede, armazenamento local e presença de aceleração por GPU ou hardware especializado.

---

## Como escolher capacidade

Ao criar uma instância EC2, não basta escolher o sistema operacional. Também é preciso escolher o tamanho e a família da máquina.

Uma aplicação que precisa de muita CPU pode usar uma família otimizada para computação. Uma aplicação que usa muita memória pode precisar de família otimizada para memória. Um workload de machine learning pode precisar de GPU.

Essa escolha afeta desempenho e custo.

---

## O que acontece na prática

Um tipo como `t3.micro` é pequeno e costuma aparecer em testes, laboratórios e cargas leves.

Tipos de famílias `m` são mais gerais. Famílias `c` favorecem computação. Famílias `r` favorecem memória. Famílias com GPU ou aceleradores aparecem em workloads gráficos, treinamento, inferência ou processamento especializado.

O nome do tipo carrega informação sobre família, geração e tamanho.

---

## Cuidado importante

Tipo de instância não é AMI.

A [[Amazon Machine Image (AMI)]] define o que vem instalado na máquina. O tipo de instância define quanta capacidade a máquina terá.

Quando a decisão envolve CPU, memória, rede, armazenamento local ou aceleradores, o tipo de instância é uma das escolhas mais importantes. Ele precisa combinar com a carga real, não apenas com o menor preço ou com o maior tamanho disponível.

Modos de Throughput do Amazon EFS definem como o [[Amazon EFS]] entrega vazão de leitura e escrita para aplicações.

O throughput é importante porque um filesystem compartilhado pode ser acessado por múltiplas instâncias, containers ou funções ao mesmo tempo. Se a vazão disponível não acompanha o padrão de acesso, a aplicação pode ficar lenta mesmo que a rede e as instâncias estejam saudáveis.

## Elastic Throughput

O modo Elastic ajusta a vazão automaticamente conforme a demanda.

É adequado quando o workload é variável, difícil de prever ou alterna entre períodos de baixo uso e picos.

Exemplo: processamento de arquivos que ocorre em horários irregulares.

---

## Provisioned Throughput

O modo Provisioned permite definir uma vazão esperada independentemente da quantidade de dados armazenados.

Ele é útil quando a aplicação precisa de throughput previsível mesmo com pouco volume armazenado.

Exemplo: uma aplicação que mantém poucos arquivos, mas lê e escreve com alta intensidade.

---

## Bursting Throughput

O modo Bursting usa um modelo em que a capacidade de burst depende do tamanho do filesystem e de créditos acumulados.

Ele funciona bem para workloads com picos ocasionais, mas pode degradar se o uso intenso for constante.

---

## Como Escolher

* demanda variável e imprevisível: Elastic.
* demanda previsível e alta: Provisioned.
* uso moderado com picos ocasionais: Bursting.


A escolha deve ser feita com métricas do [[Amazon CloudWatch]], observando throughput, latência e comportamento real da aplicação.

---

## Exemplo Prático

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Critério de Escolha

Pergunte:


* a aplicação precisa de disco?
* precisa de API de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?


Responder essas perguntas evita usar S3 como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

## Como entender isso

Este conceito pertence ao módulo de armazenamento na AWS.

## Ponto central

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via API, pense em S3. Se for filesystem compartilhado, pense em EFS ou FSx.

## Como Diferenciar

* bloco é diferente de objeto;
* objeto é diferente de arquivo compartilhado;
* classe de armazenamento altera custo e recuperação;
* lifecycle automatiza economia;
* versionamento e backup ajudam recuperação.

## Cuidado importante

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

AWS Snow Family foi o nome usado para agrupar dispositivos físicos da AWS voltados à transferência offline de dados e à execução de workloads em locais com conectividade limitada.

A família reuniu produtos como [[AWS Snowcone]], [[AWS Snowball]], [[AWS Snowball Edge]] e [[AWS Snowmobile]]. Esses nomes ainda aparecem em materiais de estudo, arquiteturas antigas e conteúdos de certificação, mas o status atual de cada oferta precisa ser observado.

---

## O que é

AWS Snow Family deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

**Situação Atual**

A AWS não oferece mais dispositivos Snow para novos clientes.

* [[AWS Snowcone]] foi descontinuado em 12 de novembro de 2024;
* [[AWS Snowmobile]] entrou em desligamento total em 14 de março de 2024;
* [[AWS Snowball Edge]] deixou de aceitar novos clientes em 7 de novembro de 2025;
* clientes que já utilizavam Snowball Edge podem continuar usando o serviço conforme as condições da AWS.

Por isso, Snow Family deve ser estudada principalmente como contexto histórico e como referência para ambientes existentes.

---

## Como funciona

**Problema que Resolvia**

Transferir centenas de terabytes ou petabytes pela rede pode levar semanas, consumir muita largura de banda e competir com o tráfego normal da empresa. Os dispositivos Snow permitiam copiar os dados localmente e enviá-los fisicamente para importação na AWS.

Alguns modelos também ofereciam capacidade computacional na borda, permitindo processar informações em fábricas, embarcações, áreas remotas ou locais temporariamente desconectados.

**Alternativas Atuais**

Para transferências online, a principal opção é o [[AWS DataSync]], normalmente combinado com [[Amazon S3]], Amazon EFS ou Amazon FSx.

Quando é necessária conectividade privada e previsível entre o ambiente local e a AWS, [[AWS Direct Connect]] pode ser mais adequado. Para transferência física segura, novos projetos devem avaliar o AWS Data Transfer Terminal ou soluções de parceiros. Para computação local gerenciada pela AWS, a alternativa indicada é o AWS Outposts.

**Como Interpretar Materiais Antigos**

A associação histórica continua útil:

* Snowcone: dispositivo pequeno e portátil;
* Snowball e Snowball Edge: transferência de grandes volumes e computação na borda;
* Snowmobile: transporte extremo de até 100 PB por unidade.

Essas associações explicam o propósito original dos produtos, mas não representam a disponibilidade comercial atual.

---

## Exemplo prático

Uma empresa pode mover dados primeiro, validar acesso, migrar uma aplicação menos crítica e só depois avançar para sistemas principais. Nesse processo, AWS Snow Family ajuda a reduzir risco e organizar a transição.

---

## Diferenças importantes

Não confunda mover para a nuvem com modernizar. Lift-and-shift muda o local de execução; refatoração muda desenho, arquitetura ou uso de serviços nativos.

---

## Cuidados

O erro comum é migrar sem validação de dependências, dados, rede, permissões, desempenho e plano de retorno. Migração precisa ser testada antes de afetar sistemas críticos.

---

## Relação com outras notas

- [[AWS Snowcone]]
- [[AWS Snowball]]
- [[AWS Snowball Edge]]
- [[AWS Snowmobile]]
- [[AWS DataSync]]
- [[Amazon S3]]
- [[AWS Direct Connect]]

TTL, ou Time To Live, define por quanto tempo uma informação pode ficar em cache antes de precisar ser consultada novamente.

Ele aparece em DNS, CDNs, caches de aplicação e outros sistemas que guardam respostas temporariamente.

---

## O que é

TTL (Time To Live) deve ser entendido como vocabulário técnico que explica um comportamento real de sistemas. O termo ajuda a nomear algo que acontece em rede, computação, dados, segurança, desempenho ou operação.

---

## Por que existe

TTL (Time To Live) existe porque sistemas complexos precisam de nomes precisos. Quando o conceito é entendido, fica mais fácil diagnosticar problemas, comparar serviços e escolher arquitetura.

---

## Como funciona

**Como o TTL controla cache**

TTL é um controle de equilíbrio.

Se o TTL é alto, uma resposta fica armazenada por mais tempo. Isso reduz consultas e pode melhorar desempenho, mas faz mudanças demorarem mais para aparecer.

Se o TTL é baixo, mudanças chegam mais rápido, mas o sistema pode precisar consultar a origem com mais frequência.

**O que acontece na prática**

Em [[DNS]], o TTL influencia por quanto tempo um resolvedor pode guardar uma resposta.

No [[Amazon CloudFront]], TTL pode influenciar quanto tempo um objeto fica em cache antes de o CloudFront verificar a origem novamente.

Esse detalhe muda a experiência do usuário, o tráfego na origem e a velocidade de propagação de mudanças.

**Exemplo com DNS e CloudFront**

Imagine que um domínio aponta para um destino antigo e você muda esse destino.

Se o TTL anterior era alto, alguns resolvedores podem continuar usando a resposta antiga por mais tempo. Se o TTL era baixo, a mudança tende a ser percebida mais rápido, mas o sistema faz mais consultas.

No [[Amazon CloudFront]], a lógica é parecida: um TTL maior reduz idas à origem, mas pode fazer o conteúdo antigo permanecer em cache por mais tempo. Um TTL menor deixa mudanças mais rápidas, mas aumenta a chance de mais requisições chegarem à origem.

Por isso, TTL é sempre uma troca entre velocidade de mudança, carga na origem e eficiência de cache.

---

## Exemplo prático

Em uma arquitetura simples, usuário, aplicação, rede, banco, armazenamento, segurança e monitoramento trabalham juntos. TTL (Time To Live) deve ser entendido pelo papel que exerce nesse conjunto.

---

## Diferenças importantes

Compare TTL (Time To Live) com termos vizinhos antes de usar a palavra como resposta. Conceitos parecidos podem atuar em camadas diferentes: aplicação, rede, armazenamento, banco, identidade ou operação.

---

## Cuidados

TTL não é tempo de vida de um servidor.

Ele é tempo de vida de uma resposta em cache.

Quando a dúvida envolve cache, DNS ou tempo para uma alteração ser percebida, o TTL costuma ser uma das primeiras configurações a verificar. Ele não garante propagação instantânea, mas influencia por quanto tempo respostas antigas podem continuar sendo reutilizadas.

---

## Relação com outras notas

- [[DNS]]
- [[Amazon CloudFront]]

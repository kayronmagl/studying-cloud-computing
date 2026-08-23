Uma CloudFront Distribution é a configuração que define como o [[Amazon CloudFront]] entrega conteúdo aos usuários.

Ela informa qual é a origem do conteúdo, como o cache funciona, quais domínios serão usados e como o tráfego será tratado nas edge locations.

---

## O que é

CloudFront Distribution deve ser entendido como vocabulário técnico que explica um comportamento real de sistemas. O termo ajuda a nomear algo que acontece em rede, computação, dados, segurança, desempenho ou operação.

---

## Por que existe

CloudFront Distribution existe porque sistemas complexos precisam de nomes precisos. Quando o conceito é entendido, fica mais fácil diagnosticar problemas, comparar serviços e escolher arquitetura.

---

## Como funciona

**Como a distribuição funciona**

O CloudFront é a CDN. A distribution é a configuração concreta dentro do serviço.

Uma distribuição pode apontar para uma origem como [[Amazon S3]], um load balancer, uma aplicação web ou outro endpoint HTTP.

A partir dessa configuração, o CloudFront passa a receber requisições dos usuários e entregar conteúdo usando sua rede global de borda.

**O que acontece na prática**

Imagine um site que guarda imagens em [[Amazon S3|S3]].

Você cria uma distribution apontando para o [[Buckets S3|bucket]] como origem. Quando usuários acessam as imagens, o CloudFront pode guardar cópias em locais de borda próximos aos usuários.

Isso reduz latência e diminui carga sobre a origem.

---

## Exemplo prático

Em uma arquitetura simples, usuário, aplicação, rede, banco, armazenamento, segurança e monitoramento trabalham juntos. CloudFront Distribution deve ser entendido pelo papel que exerce nesse conjunto.

---

## Diferenças importantes

Compare CloudFront Distribution com termos vizinhos antes de usar a palavra como resposta. Conceitos parecidos podem atuar em camadas diferentes: aplicação, rede, armazenamento, banco, identidade ou operação.

---

## Cuidados

CloudFront Distribution não é a mesma coisa que [[Buckets S3|bucket S3]].

O [[Buckets S3|bucket]] guarda objetos. A distribuição define como esses objetos serão entregues pela CDN.

Quando a dúvida envolve origem, comportamento de cache, domínio, certificado ou entrega por edge locations, a distribuição é o ponto de configuração que precisa ser analisado.

---

## Relação com outras notas

- [[Amazon CloudFront]]
- [[Amazon S3]]

Uma CloudFront Distribution é a configuração que define como o [[Amazon CloudFront]] entrega conteúdo aos usuários.

Ela informa qual é a origem do conteúdo, como o cache funciona, quais domínios serão usados e como o tráfego será tratado nas edge locations.

---

## Visão geral

O CloudFront é a CDN. A distribution é a configuração concreta dentro do serviço.

Uma distribuição pode apontar para uma origem como [[Amazon S3]], um load balancer, uma aplicação web ou outro endpoint HTTP.

A partir dessa configuração, o CloudFront passa a receber requisições dos usuários e entregar conteúdo usando sua rede global de borda.

---

## O que acontece na prática

Imagine um site que guarda imagens em S3.

Você cria uma distribution apontando para o bucket como origem. Quando usuários acessam as imagens, o CloudFront pode guardar cópias em locais de borda próximos aos usuários.

Isso reduz latência e diminui carga sobre a origem.

---

## Cuidado importante

CloudFront Distribution não é a mesma coisa que bucket S3.

O bucket guarda objetos. A distribuição define como esses objetos serão entregues pela CDN.

Quando o cenário envolve em configuração de CDN, origem, cache behavior ou entrega por edge locations, CloudFront Distribution costuma ser a associação mais direta.

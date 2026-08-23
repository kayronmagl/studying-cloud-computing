Amazon CloudFront é a CDN da AWS.

Ele entrega conteúdo por [[Edge Locations]] e pontos de presença próximos ao usuário, reduzindo [[Latência]] e carga na origem.

---

## O que é

CloudFront é uma CDN.

Ele mantém cópias de conteúdo em edge locations próximas aos usuários, reduzindo latência e carga na origem.

---

## Por que existe

Amazon CloudFront existe para resolver uma limitação prática de sistemas: executar, armazenar, conectar, proteger, observar, escalar ou governar recursos.

---

## Como funciona

**Distribution, Origin e Cache**

Uma [[CloudFront Distribution]] define origens, domínios, certificados e regras. A Origin pode ser [[Amazon S3]], [[Elastic Load Balancing]], [[Amazon EC2]] ou uma [[APIs|API]]. Cache Behavior e [[TTL (Time To Live)]] controlam como cada caminho é armazenado.

---

## Exemplo prático

Arquivos estáticos ficam no [[Amazon S3|S3]]. CloudFront distribui cópias em borda. Usuários recebem conteúdo de um ponto próximo, melhorando RTT e experiência.

---

## Diferenças importantes

**Pontos que Costumam Gerar Confusão**

CloudFront apareceu em duas ideias:

* entregar conteúdo por uma rede global de locais de borda;
* reduzir latência e aumentar velocidade para site estático hospedado em [[Amazon S3|S3]].

---

## Cuidados

**Segurança**

CloudFront pode usar HTTPS, [[AWS WAF]], logs, restrição geográfica e controle de acesso à origem. Com [[Amazon S3|S3]], é comum bloquear acesso público direto ao [[Buckets S3|bucket]] e permitir acesso apenas via CloudFront.

CloudFront não cria [[Amazon VPC|VPC]].

CloudFront não é banco.

CloudFront não transfere 100 PB para AWS.

CloudFront entrega conteúdo aos usuários.

---

## Relação com outras notas

- [[Edge Locations]]
- [[Latência]]
- [[CloudFront Distribution]]
- [[Amazon S3]]
- [[Elastic Load Balancing]]
- [[Amazon EC2]]
- [[TTL (Time To Live)]]
- [[AWS WAF]]

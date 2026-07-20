Amazon CloudFront é a CDN da AWS.

Ele entrega conteúdo por [[Edge Locations]] e pontos de presença próximos ao usuário, reduzindo [[Latência]] e carga na origem.

## Distribution, Origin e Cache

Uma [[CloudFront Distribution]] define origens, domínios, certificados e regras. A Origin pode ser [[Amazon S3]], [[Elastic Load Balancing]], [[Amazon EC2]] ou uma API. Cache Behavior e [[TTL (Time To Live)]] controlam como cada caminho é armazenado.

---

## Segurança

CloudFront pode usar HTTPS, [[AWS WAF]], logs, restrição geográfica e controle de acesso à origem. Com S3, é comum bloquear acesso público direto ao bucket e permitir acesso apenas via CloudFront.

---

## Exemplo

Arquivos estáticos ficam no S3. CloudFront distribui cópias em borda. Usuários recebem conteúdo de um ponto próximo, melhorando RTT e experiência.

## Pontos que Costumam Gerar Confusão

CloudFront apareceu em duas ideias:

* entregar conteúdo por uma rede global de locais de borda;
* reduzir latência e aumentar velocidade para site estático hospedado em S3.

---

## Como entender

CloudFront é uma CDN.

Ele mantém cópias de conteúdo em edge locations próximas aos usuários, reduzindo latência e carga na origem.

---

## Cuidado importante na prática

CloudFront não cria VPC.

CloudFront não é banco.

CloudFront não transfere 100 PB para AWS.

CloudFront entrega conteúdo aos usuários.

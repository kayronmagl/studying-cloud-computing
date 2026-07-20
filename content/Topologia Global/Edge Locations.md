Edge Locations são pontos de presença próximos aos usuários. Sustentam serviços como [[Amazon CloudFront]], cache, segurança de borda e baixa latência.

---

## Visão geral

Edge Locations é uma ideia de localização, falha ou distribuição. Quando estudar, pergunte: “onde o recurso fica?” e “o que acontece se uma parte falhar?”.

Esse raciocínio é essencial para entender alta disponibilidade, disaster recovery e latência.

---

## Exemplo Prático

Uma aplicação pode executar instâncias em duas zonas de disponibilidade. Se uma zona sofrer falha, o tráfego pode ser direcionado para recursos saudáveis em outra zona.

Esse desenho depende de conceitos como isolamento, latência, failover, replicação e estado da aplicação.

---

## Decisão Arquitetural

Ao escolher região, zona ou estratégia de recuperação, a equipe precisa equilibrar:

* latência para usuários;
* custo;
* conformidade legal;
* disponibilidade desejada;
* complexidade operacional;
* tolerância à perda de dados.

Não basta “usar AWS”. É necessário desenhar onde e como os recursos serão distribuídos.

---

## Exemplo Arquitetural

Uma aplicação crítica pode usar duas zonas de disponibilidade, um load balancer, bancos Multi-AZ e backups. Se um componente falhar, o tráfego deve continuar indo para partes saudáveis.

---

## Cuidados importantes

Distribuir recursos aumenta disponibilidade, mas também pode aumentar custo e complexidade.

A decisão precisa equilibrar latência, custo, conformidade, RTO, RPO e esforço operacional.

## Processamento próximo do usuário

[[Edge Computing]] aproxima parte do processamento do usuário final para reduzir latência e melhorar experiência.

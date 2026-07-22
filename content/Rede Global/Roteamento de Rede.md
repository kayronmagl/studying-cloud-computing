Roteamento de Rede escolhe caminhos para pacotes. Na AWS, aparece em [[Route Tables]], VPCs, redes globais e conectividade híbrida.

## Exemplo Prático

Quando um usuário acessa uma aplicação hospedada na AWS, a requisição pode passar pela internet pública, por redes de telecomunicação, por edge locations, por uma CDN, por um load balancer e finalmente por recursos dentro de uma VPC.

Cada etapa pode melhorar ou piorar a experiência.

---

## Cuidados importantes

Problemas de rede nem sempre aparecem como “rede fora”. Muitas vezes aparecem como latência alta, timeout, perda de pacotes, gargalo de throughput, cache mal configurado ou custo de transferência inesperado.

Por isso, entender este conceito ajuda a interpretar desempenho e disponibilidade de aplicações em nuvem.

---

## Exemplo

Uma aplicação pode usar CloudFront para reduzir latência, WAF para filtrar tráfego malicioso e Route 53 para direcionar usuários ao endpoint adequado.

Sem esses componentes, todo tráfego pode depender diretamente de uma origem distante e mais sensível a picos.

---

## Cuidado adicional

Problemas de rede aparecem como lentidão, timeouts, custo alto, cache errado ou indisponibilidade parcial.

Por isso, rede global precisa ser observada com métricas e logs.

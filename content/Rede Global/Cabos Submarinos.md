Cabos Submarinos são fibras ópticas oceânicas que conectam continentes. Eles sustentam grande parte do tráfego global e da conectividade entre regiões.

---

## Visão geral

Cabos Submarinos ajuda a entender o caminho dos dados. Em nuvem, desempenho e disponibilidade dependem muito de como o tráfego sai do usuário, passa pela rede e chega ao serviço.

Sempre associe este conceito a latência, roteamento, cache, segurança ou entrega de conteúdo.

---

## Exemplo Prático

Quando um usuário acessa uma aplicação hospedada na AWS, a requisição pode passar pela internet pública, por redes de telecomunicação, por edge locations, por uma CDN, por um load balancer e finalmente por recursos dentro de uma VPC.

Cada etapa pode melhorar ou piorar a experiência.

---

## Cuidados importantes

Problemas de rede nem sempre aparecem como “rede fora”. Muitas vezes aparecem como latência alta, timeout, perda de pacotes, gargalo de throughput, cache mal configurado ou custo de transferência inesperado.

Por isso, entender este conceito ajuda a interpretar desempenho e disponibilidade de aplicações em nuvem.

---

## Exemplo Arquitetural

Uma aplicação pode usar CloudFront para reduzir latência, WAF para filtrar tráfego malicioso e Route 53 para direcionar usuários ao endpoint adequado.

Sem esses componentes, todo tráfego pode depender diretamente de uma origem distante e mais sensível a picos.

---

## Cuidado adicional

Problemas de rede aparecem como lentidão, timeouts, custo alto, cache errado ou indisponibilidade parcial.

Por isso, rede global precisa ser observada com métricas e logs.

## Capacidade em fibras ópticas

[[DWDM]] aparece em redes de longa distância porque permite transportar múltiplos comprimentos de onda pela mesma fibra óptica.

---

## Fibra dedicada ou não iluminada

[[Dark Fiber]] ajuda a entender capacidade de rede ainda não ativada ou dedicada para comunicação de alta capacidade.

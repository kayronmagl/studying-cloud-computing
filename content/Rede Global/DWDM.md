DWDM é multiplexação por divisão densa de comprimento de onda. Permite transmitir múltiplos sinais ópticos pela mesma fibra.

---

## O que é

DWDM deve ser entendido como parte da entrega de tráfego em escala global. Distância, roteamento, DNS, cache, CDN e pontos de borda influenciam a experiência do usuário tanto quanto o servidor de origem.

---

## Por que existe

DWDM existe para explicar como localização, distância, redundância, cache, conectividade e distribuição geográfica afetam disponibilidade, latência, recuperação e custo.

---

## Como funciona

DWDM funciona por distribuição, cache, resolução de nomes, roteamento, políticas de origem, validade de conteúdo e observação do tráfego. O ganho depende do tipo de dado e do padrão de acesso.

---

## Exemplo prático

Quando um usuário acessa uma aplicação hospedada na AWS, a requisição pode passar pela internet pública, por redes de telecomunicação, por edge locations, por uma CDN, por um load balancer e finalmente por recursos dentro de uma [[Amazon VPC|VPC]].

Cada etapa pode melhorar ou piorar a experiência.

Uma aplicação pode usar CloudFront para reduzir latência, WAF para filtrar tráfego malicioso e Route 53 para direcionar usuários ao endpoint adequado.

Sem esses componentes, todo tráfego pode depender diretamente de uma origem distante e mais sensível a picos.

---

## Diferenças importantes

Compare DWDM com região, edge, CDN, DNS, cache e roteamento. CDN entrega conteúdo; DNS resolve nomes; cache guarda cópias; roteamento decide caminhos; região executa serviços principais.

---

## Cuidados

Problemas de rede nem sempre aparecem como “rede fora”. Muitas vezes aparecem como latência alta, timeout, perda de pacotes, gargalo de throughput, cache mal configurado ou custo de transferência inesperado.

Por isso, entender este conceito ajuda a interpretar desempenho e disponibilidade de aplicações em nuvem.

Problemas de rede aparecem como lentidão, timeouts, custo alto, cache errado ou indisponibilidade parcial.

Por isso, rede global precisa ser observada com métricas e logs.

---

## Relação com outras notas

- [[O que é computação em nuvem]]
- [[Regions (Regiões)]]
- [[Availability Zones (AZ)]]
- [[Edge Locations]]

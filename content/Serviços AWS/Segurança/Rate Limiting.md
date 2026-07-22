Rate Limiting é a prática de limitar a quantidade de requisições permitidas por origem, identidade, rota ou padrão.

Na AWS, pode ser aplicado com [[AWS WAF]], [[Amazon API Gateway]], aplicações próprias e outros componentes.


Em Rate Limiting, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Por que Importa

Rate limiting ajuda contra:

* abuso;
* scraping;
* brute force;
* picos maliciosos;
* consumo indevido de APIs;
* ataques de camada 7;
* erros de clientes em loop.

---

## Exemplo

* se um IP fizer mais de 1000 requisições em 5 minutos: bloquear ou desafiar.


---

## Limite

Rate limiting não substitui autenticação, autorização ou proteção DDoS.

Ele é uma camada de controle de abuso.

---

## Cuidado

Limites agressivos podem prejudicar usuários legítimos atrás de NAT, proxies corporativos ou redes móveis.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Como entender isso

Este conceito pertence ao módulo de segurança na AWS.

## Ponto central

Segurança combina IAM, rede, criptografia, auditoria, detecção e proteção de aplicação.

## Como Diferenciar

* IAM controla permissões.
* KMS gerencia chaves.
* WAF filtra HTTP/HTTPS.
* Shield protege contra DDoS.
* CloudTrail audita chamadas de API.
* GuardDuty detecta ameaças.

## Cuidado importante

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

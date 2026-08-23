Rate Limiting é a prática de limitar a quantidade de requisições permitidas por origem, identidade, rota ou padrão.

Na AWS, pode ser aplicado com [[AWS WAF]], [[Amazon API Gateway]], aplicações próprias e outros componentes.

Em Rate Limiting, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Rate Limiting deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Rate limiting ajuda contra:

* abuso;
* scraping;
* brute force;
* picos maliciosos;
* consumo indevido de [[APIs|APIs]];
* ataques de camada 7;
* erros de clientes em loop.

---

## Como funciona

O funcionamento depende de políticas, identidades, permissões, registros de auditoria e integração com outros controles. Ao estudar Rate Limiting, observe sempre quem pode executar a ação, sobre qual recurso, em qual condição e como isso fica registrado.

---

## Exemplo prático

* se um IP fizer mais de 1000 requisições em 5 minutos: bloquear ou desafiar.

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Como Diferenciar**

* [[AWS Identity and Access Management (IAM)|IAM]] controla permissões.
* KMS gerencia chaves.
* WAF filtra HTTP/HTTPS.
* Shield protege contra DDoS.
* CloudTrail audita chamadas de [[APIs|API]].
* GuardDuty detecta ameaças.

---

## Cuidados

**Limite**

Rate limiting não substitui autenticação, autorização ou proteção DDoS.

Ele é uma camada de controle de abuso.

Limites agressivos podem prejudicar usuários legítimos atrás de NAT, proxies corporativos ou redes móveis.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[AWS WAF]]
- [[Amazon API Gateway]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]

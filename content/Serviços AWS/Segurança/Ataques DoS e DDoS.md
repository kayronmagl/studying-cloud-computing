Ataques DoS e DDoS tentam tornar um serviço indisponível. DoS significa Denial of Service. [[DDoS]] significa Distributed Denial of Service.

A diferença principal é que DDoS usa múltiplas origens distribuídas para aumentar volume e dificultar bloqueio.


Em Ataques DoS e DDoS, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Camadas

Ataques podem ocorrer em diferentes camadas:

* camada de rede;
* camada de transporte;
* camada de aplicação.

Ataques volumétricos tentam saturar capacidade. Ataques de aplicação tentam consumir recursos do backend com requisições aparentemente válidas.

---

## Impactos

* indisponibilidade;
* aumento de latência;
* custo elevado;
* saturação de instâncias;
* degradação de banco;
* falhas em cascata.

---

## Defesa em AWS

A defesa combina:

* [[AWS Shield]];
* [[AWS WAF]];
* [[Amazon CloudFront]];
* [[Elastic Load Balancing]];
* [[Amazon Route 53]];
* escalabilidade;
* rate limiting;
* arquitetura multi-AZ;
* logs e alarmes.

---

## Cuidado

Não existe botão único contra DDoS.

Proteção depende de arquitetura, borda, absorção, filtragem, observabilidade e resposta.

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

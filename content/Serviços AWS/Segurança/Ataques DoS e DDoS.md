Ataques DoS e DDoS tentam tornar um serviço indisponível. DoS significa Denial of Service. [[DDoS]] significa Distributed Denial of Service.

A diferença principal é que DDoS usa múltiplas origens distribuídas para aumentar volume e dificultar bloqueio.

Em Ataques DoS e DDoS, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Ataques DoS e DDoS deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Ataques DoS e DDoS existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Camadas**

Ataques podem ocorrer em diferentes camadas:

* camada de rede;
* camada de transporte;
* camada de aplicação.

Ataques volumétricos tentam saturar capacidade. Ataques de aplicação tentam consumir recursos do backend com requisições aparentemente válidas.

**Impactos**

* indisponibilidade;
* aumento de latência;
* custo elevado;
* saturação de instâncias;
* degradação de banco;
* falhas em cascata.

**Defesa em AWS**

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

## Exemplo prático

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

Não existe botão único contra DDoS.

Proteção depende de arquitetura, borda, absorção, filtragem, observabilidade e resposta.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[DDoS]]
- [[AWS Shield]]
- [[AWS WAF]]
- [[Amazon CloudFront]]
- [[Elastic Load Balancing]]
- [[Amazon Route 53]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]

Criptografia em Trânsito protege dados enquanto trafegam entre clientes, aplicações, serviços, redes e [[APIs|APIs]].

Ela normalmente é implementada com TLS, o protocolo usado por HTTPS para proteger confidencialidade e integridade durante a comunicação.

Em Criptografia em Trânsito, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Criptografia em Trânsito deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Sem criptografia em trânsito, dados podem ser interceptados ou manipulados no caminho.

Exemplos de dados sensíveis em trânsito:

* credenciais;
* tokens;
* dados pessoais;
* payloads de [[APIs|APIs]];
* consultas a bancos;
* arquivos enviados por usuários;
* respostas de aplicações.

---

## Como funciona

**Onde Aparece na AWS**

Criptografia em trânsito aparece em:

* conexões HTTPS com [[Amazon CloudFront]];
* [[APIs|APIs]] expostas por [[Amazon API Gateway]];
* aplicações atrás de [[Elastic Load Balancing]];
* conexões com [[Amazon RDS]];
* acesso a objetos no [[Amazon S3]];
* chamadas para [[APIs]];
* comunicação entre serviços.

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Diferença para Criptografia em Repouso**

[[Criptografia em Repouso]] protege dados armazenados.

Criptografia em trânsito protege dados durante comunicação.

As duas são necessárias, porque um dado pode estar protegido no disco e ainda ser exposto se trafegar sem TLS.

**Como Diferenciar**

* [[AWS Identity and Access Management (IAM)|IAM]] controla permissões.
* KMS gerencia chaves.
* WAF filtra HTTP/HTTPS.
* Shield protege contra DDoS.
* CloudTrail audita chamadas de [[APIs|API]].
* GuardDuty detecta ameaças.

---

## Cuidados

TLS não substitui autenticação, autorização, validação de entrada ou proteção contra abuso.

Ele protege o canal, mas não garante que o usuário tem permissão correta para acessar o dado.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com ACM**

[[AWS Certificate Manager (ACM)]] facilita provisionar e renovar certificados TLS usados por serviços AWS compatíveis.

Isso reduz risco operacional de certificados expirados ou mal gerenciados.

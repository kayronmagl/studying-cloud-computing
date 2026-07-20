Criptografia em Trânsito protege dados enquanto trafegam entre clientes, aplicações, serviços, redes e APIs.

Ela normalmente é implementada com TLS, o protocolo usado por HTTPS para proteger confidencialidade e integridade durante a comunicação.

---

## Visão geral

Em Criptografia em Trânsito, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Problema que Resolve

Sem criptografia em trânsito, dados podem ser interceptados ou manipulados no caminho.

Exemplos de dados sensíveis em trânsito:

* credenciais;
* tokens;
* dados pessoais;
* payloads de APIs;
* consultas a bancos;
* arquivos enviados por usuários;
* respostas de aplicações.

---

## Onde Aparece na AWS

Criptografia em trânsito aparece em:

* conexões HTTPS com [[Amazon CloudFront]];
* APIs expostas por [[Amazon API Gateway]];
* aplicações atrás de [[Elastic Load Balancing]];
* conexões com [[Amazon RDS]];
* acesso a objetos no [[Amazon S3]];
* chamadas para [[APIs]];
* comunicação entre serviços.

---

## Relação com ACM

[[AWS Certificate Manager (ACM)]] facilita provisionar e renovar certificados TLS usados por serviços AWS compatíveis.

Isso reduz risco operacional de certificados expirados ou mal gerenciados.

---

## Diferença para Criptografia em Repouso

[[Criptografia em Repouso]] protege dados armazenados.

Criptografia em trânsito protege dados durante comunicação.

As duas são necessárias, porque um dado pode estar protegido no disco e ainda ser exposto se trafegar sem TLS.

---

## Cuidado

TLS não substitui autenticação, autorização, validação de entrada ou proteção contra abuso.

Ele protege o canal, mas não garante que o usuário tem permissão correta para acessar o dado.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

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

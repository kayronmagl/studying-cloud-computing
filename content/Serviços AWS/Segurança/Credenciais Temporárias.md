Credenciais Temporárias são credenciais com tempo de expiração.

Na AWS, elas são frequentemente emitidas pelo [[AWS Security Token Service (STS)]] quando uma entidade assume uma [[Roles do IAM|role]].


Em Credenciais Temporárias, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Por que São Melhores

Se uma credencial temporária vaza, ela deixa de funcionar após expirar.

Isso reduz janela de exploração.

---

## Uso em Serviços

Serviços como [[Amazon EC2]] e [[AWS Lambda]] podem usar roles para obter credenciais temporárias sem armazenar chaves no código.

---

## Exemplo

Uma aplicação em EC2 precisa ler S3.

Em vez de colocar access key no servidor, associa-se uma role à instância. A AWS fornece credenciais temporárias automaticamente.

---

## Limite

Credenciais temporárias não corrigem permissões amplas.

Se a role permite demais, o risco continua alto durante a validade da credencial.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

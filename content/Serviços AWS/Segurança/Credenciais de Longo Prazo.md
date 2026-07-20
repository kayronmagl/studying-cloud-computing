Credenciais de Longo Prazo são credenciais que permanecem válidas até serem removidas, expiradas manualmente ou rotacionadas.

Na AWS, exemplos comuns são senhas de usuários IAM e access keys.

---

## Visão geral

Em Credenciais de Longo Prazo, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Risco

Credenciais longas podem vazar em:

* repositórios Git;
* máquinas de desenvolvedores;
* logs;
* variáveis de ambiente;
* imagens de containers;
* arquivos de configuração;
* ferramentas de CI/CD.

Se não houver rotação ou monitoramento, o acesso pode permanecer ativo por muito tempo.

---

## Alternativa

Para aplicações, prefira [[Roles do IAM]] e credenciais temporárias emitidas pelo [[AWS Security Token Service (STS)]].

---

## Boa Prática

Use credenciais permanentes apenas quando necessário.

Quando usar, aplique menor privilégio, rotação, monitoramento e remoção de credenciais sem uso.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

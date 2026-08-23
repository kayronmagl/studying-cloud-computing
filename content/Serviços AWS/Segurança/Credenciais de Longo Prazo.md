Credenciais de Longo Prazo são credenciais que permanecem válidas até serem removidas, expiradas manualmente ou rotacionadas.

Na AWS, exemplos comuns são senhas de usuários [[AWS Identity and Access Management (IAM)|IAM]] e access keys.

Em Credenciais de Longo Prazo, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Credenciais de Longo Prazo deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

---

## Por que existe

Credenciais de Longo Prazo existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Risco**

Credenciais longas podem vazar em:

* repositórios Git;
* máquinas de desenvolvedores;
* logs;
* variáveis de ambiente;
* imagens de containers;
* arquivos de configuração;
* ferramentas de CI/CD.

Se não houver rotação ou monitoramento, o acesso pode permanecer ativo por muito tempo.

**Alternativa**

Para aplicações, prefira [[Roles do IAM]] e credenciais temporárias emitidas pelo [[AWS Security Token Service (STS)]].

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

Não confunda controles de segurança diferentes. [[AWS Identity and Access Management (IAM)|IAM]] decide permissões, KMS protege chaves, CloudTrail registra ações, GuardDuty detecta comportamento suspeito, WAF filtra tráfego de aplicação e Shield atua contra DDoS.

---

## Cuidados

**Boa Prática**

Use credenciais permanentes apenas quando necessário.

Quando usar, aplique menor privilégio, rotação, monitoramento e remoção de credenciais sem uso.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Relação com outras notas

- [[Roles do IAM]]
- [[AWS Security Token Service (STS)]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]

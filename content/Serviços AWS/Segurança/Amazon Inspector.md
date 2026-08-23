Amazon Inspector é o serviço da AWS para gerenciamento de vulnerabilidades.

Ele ajuda a identificar vulnerabilidades e exposições em workloads como instâncias, imagens de containers e funções [[AWS Lambda|Lambda]], conforme suporte do serviço.

Em Amazon Inspector, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Amazon Inspector deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Amazon Inspector existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Papel**

Inspector avalia pacotes, software e configurações para encontrar riscos conhecidos.

---

## Exemplo prático

Uma imagem de container usada por uma aplicação pode conter uma biblioteca com CVE crítica.

Inspector ajuda a detectar isso para correção.

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

Encontrar vulnerabilidade não corrige automaticamente.

A equipe precisa atualizar dependências, imagens, pacotes ou código.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com Aplicações**

Inspector complementa [[Segurança de Aplicações na AWS]], mas não substitui testes de aplicação, revisão de código ou correção de lógica insegura.

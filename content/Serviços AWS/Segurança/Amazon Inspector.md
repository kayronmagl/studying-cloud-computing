Amazon Inspector é o serviço da AWS para gerenciamento de vulnerabilidades.

Ele ajuda a identificar vulnerabilidades e exposições em workloads como instâncias, imagens de containers e funções Lambda, conforme suporte do serviço.


Em Amazon Inspector, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Papel

Inspector avalia pacotes, software e configurações para encontrar riscos conhecidos.

---

## Exemplo

Uma imagem de container usada por uma aplicação pode conter uma biblioteca com CVE crítica.

Inspector ajuda a detectar isso para correção.

---

## Relação com Aplicações

Inspector complementa [[Segurança de Aplicações na AWS]], mas não substitui testes de aplicação, revisão de código ou correção de lógica insegura.

---

## Cuidado

Encontrar vulnerabilidade não corrige automaticamente.

A equipe precisa atualizar dependências, imagens, pacotes ou código.

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

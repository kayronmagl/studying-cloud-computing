Autenticação Multifator, ou MFA, adiciona uma segunda prova de identidade além da senha.

Na AWS, MFA é especialmente importante para o usuário root, usuários administrativos e operações sensíveis.

Em Autenticação Multifator (MFA), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Autenticação Multifator (MFA) deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Senha pode vazar.

MFA reduz risco porque o atacante também precisaria do segundo fator.

---

## Como funciona

**Fatores**

Exemplos de fatores:

* aplicativo autenticador;
* chave física;
* token;
* mecanismo compatível com MFA.

**Uso na AWS**

MFA pode ser exigido para login e também em políticas [[AWS Identity and Access Management (IAM)|IAM]] usando condições.

Exemplo: permitir uma ação administrativa apenas se a sessão foi autenticada com MFA.

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

**Boa Prática**

Ative MFA no [[Usuário Root da Conta AWS]] e em identidades com privilégios elevados.

Não trate MFA como opcional em contas reais.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
- [[Usuário Root da Conta AWS]]

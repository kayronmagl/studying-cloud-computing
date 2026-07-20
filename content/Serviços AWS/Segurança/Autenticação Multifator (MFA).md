Autenticação Multifator, ou MFA, adiciona uma segunda prova de identidade além da senha.

Na AWS, MFA é especialmente importante para o usuário root, usuários administrativos e operações sensíveis.

---

## Visão geral

Em Autenticação Multifator (MFA), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Por que Importa

Senha pode vazar.

MFA reduz risco porque o atacante também precisaria do segundo fator.

---

## Fatores

Exemplos de fatores:

* aplicativo autenticador;
* chave física;
* token;
* mecanismo compatível com MFA.

---

## Uso na AWS

MFA pode ser exigido para login e também em políticas IAM usando condições.

Exemplo: permitir uma ação administrativa apenas se a sessão foi autenticada com MFA.

---

## Boa Prática

Ative MFA no [[Usuário Root da Conta AWS]] e em identidades com privilégios elevados.

Não trate MFA como opcional em contas reais.

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

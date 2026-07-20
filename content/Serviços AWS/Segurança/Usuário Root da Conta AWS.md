O Usuário Root da Conta AWS é a identidade original da conta AWS.

Ele possui acesso total à conta e a recursos críticos de faturamento, segurança e configuração.

---

## Visão geral

Em Usuário Root da Conta AWS, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Por que é Sensível

O root pode executar ações que nenhuma outra identidade deveria usar no dia a dia.

Se comprometido, o impacto pode ser extremo.

---

## Boas Práticas

* ativar [[Autenticação Multifator (MFA)]];
* não usar root para tarefas diárias;
* proteger e-mail associado;
* não criar access keys para root;
* usar usuários, roles e IAM Identity Center para operação;
* monitorar uso.

---

## Quando Usar

Root deve ser reservado para tarefas raras que realmente exigem root, como certas configurações de conta.

---

## Relação com IAM

O trabalho diário deve ser feito por identidades controladas pelo [[AWS Identity and Access Management (IAM)|IAM]], com permissões mínimas.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Cuidado importante

O usuário root tem poder total sobre a conta.

Ele deve ser usado o mínimo possível e protegido com MFA. Atividades do dia a dia devem ser feitas com usuários, roles e permissões específicas no IAM.

Se alguém compromete o root, o risco é muito maior do que comprometer uma identidade limitada por políticas.

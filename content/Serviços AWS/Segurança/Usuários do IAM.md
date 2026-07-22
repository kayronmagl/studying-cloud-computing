Usuários do IAM são identidades permanentes criadas dentro de uma conta AWS.

Um usuário pode representar uma pessoa, um administrador, um operador ou uma integração técnica. Ele pode ter senha para o [[AWS Management Console]] e/ou [[Access Keys|access keys]] para acesso programático por [[AWS CLI]], [[AWS SDKs]] e [[APIs]].


Em Usuários do IAM, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Quando Usar

Usuários do IAM ainda aparecem em cenários como:

* contas de laboratório;
* usuários administrativos específicos;
* integrações legadas;
* ambientes simples;
* aprendizado.

Mas para workloads e aplicações, [[Roles do IAM]] geralmente são mais seguras.

---

## Risco de [[Credenciais de Longo Prazo|Credenciais Permanentes]]

Usuários podem ter access keys de longo prazo.

Se essas chaves vazam em código, repositórios, logs ou máquinas comprometidas, um atacante pode acessar a conta dentro das permissões do usuário.

Por isso, access keys precisam de rotação, monitoramento e escopo mínimo.

---

## Boas Práticas

* usar [[Autenticação Multifator (MFA)]];
* evitar permissões administrativas amplas;
* preferir grupos para permissões;
* remover usuários sem uso;
* evitar access keys desnecessárias;
* monitorar uso via [[AWS CloudTrail]].

---

## Relação com IAM Identity Center

Em organizações maiores, o ideal costuma ser centralizar acesso humano com IAM Identity Center ou federação, reduzindo usuários IAM individuais para pessoas.

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

Usuários do [[AWS Identity and Access Management (IAM)|IAM]] são identidades permanentes criadas dentro de uma conta AWS.

Um usuário pode representar uma pessoa, um administrador, um operador ou uma integração técnica. Ele pode ter senha para o [[AWS Management Console]] e/ou [[Access Keys|access keys]] para acesso programático por [[AWS CLI]], [[AWS SDKs]] e [[APIs]].

Em Usuários do [[AWS Identity and Access Management (IAM)|IAM]], pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Usuários do IAM deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Usuários do [[AWS Identity and Access Management (IAM)|IAM]] existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Risco de [[Credenciais de Longo Prazo|Credenciais Permanentes]]**

Usuários podem ter access keys de longo prazo.

Se essas chaves vazam em código, repositórios, logs ou máquinas comprometidas, um atacante pode acessar a conta dentro das permissões do usuário.

Por isso, access keys precisam de rotação, monitoramento e escopo mínimo.

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

**Quando Usar**

Usuários do [[AWS Identity and Access Management (IAM)|IAM]] ainda aparecem em cenários como:

* contas de laboratório;
* usuários administrativos específicos;
* integrações legadas;
* ambientes simples;
* aprendizado.

Mas para workloads e aplicações, [[Roles do IAM]] geralmente são mais seguras.

**Como Diferenciar**

* [[AWS Identity and Access Management (IAM)|IAM]] controla permissões.
* KMS gerencia chaves.
* WAF filtra HTTP/HTTPS.
* Shield protege contra DDoS.
* CloudTrail audita chamadas de [[APIs|API]].
* GuardDuty detecta ameaças.

---

## Cuidados

**Boas Práticas**

* usar [[Autenticação Multifator (MFA)]];
* evitar permissões administrativas amplas;
* preferir grupos para permissões;
* remover usuários sem uso;
* evitar access keys desnecessárias;
* monitorar uso via [[AWS CloudTrail]].

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com [[AWS Identity and Access Management (IAM)|IAM]] Identity Center**

Em organizações maiores, o ideal costuma ser centralizar acesso humano com [[AWS Identity and Access Management (IAM)|IAM]] Identity Center ou federação, reduzindo usuários [[AWS Identity and Access Management (IAM)|IAM]] individuais para pessoas.

- [[AWS Management Console]]
- [[Access Keys]]
- [[AWS CLI]]
- [[AWS SDKs]]
- [[APIs]]
- [[Credenciais de Longo Prazo]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]

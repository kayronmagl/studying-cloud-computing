AWS Organizations é o serviço usado para organizar múltiplas contas AWS em uma estrutura centralizada.

Ele permite agrupar contas, aplicar políticas e separar ambientes como produção, desenvolvimento, segurança, auditoria e dados.

Em AWS Organizations, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

AWS Organizations deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

Organizations permite criar e organizar contas, aplicar políticas, usar faturamento consolidado e estruturar governança multi-conta.

---

## Por que existe

AWS Organizations existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Por que Usar Múltiplas Contas**

Separar contas reduz blast radius.

Um problema em desenvolvimento não deve comprometer produção. Uma conta de segurança pode centralizar logs e auditoria.

**Organizational Units**

Contas podem ser agrupadas em unidades organizacionais.

Exemplo:

* Root: Produção.
* Desenvolvimento: Segurança.
* Logs: Sandbox.

**SCPs**

Com [[Service Control Policies (SCPs)]], a organização define limites máximos de permissão para contas ou unidades.

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

**Pontos que Costumam Gerar Confusão**

Quando o cenário envolve consolidar e gerenciar várias contas AWS em um local central, a resposta é [[AWS Organizations]].

---

## Cuidados

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

[[AWS Identity and Access Management (IAM)|IAM]] gerencia identidades e permissões.

Organizations gerencia múltiplas contas AWS.

---

## Relação com outras notas

**Relação com Segurança**

Organizations é base para governança em ambientes profissionais.

Ele permite separar responsabilidades, aplicar controles centrais e reduzir risco entre ambientes.

**Relação com Gestão Financeira**

* [[Faturamento Consolidado da AWS]];
* [[AWS Control Tower]];

**Relação com AWS CAF**

Este conceito também aparece em discussões de adoção de nuvem dentro do [[AWS Cloud Adoption Framework (AWS CAF)]], especialmente quando a organização precisa criar governança, plataforma e operação consistentes para usar AWS em escala.

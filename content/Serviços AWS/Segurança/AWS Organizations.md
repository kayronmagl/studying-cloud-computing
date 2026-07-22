AWS Organizations é o serviço usado para organizar múltiplas contas AWS em uma estrutura centralizada.

Ele permite agrupar contas, aplicar políticas e separar ambientes como produção, desenvolvimento, segurança, auditoria e dados.


Em AWS Organizations, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Por que Usar Múltiplas Contas

Separar contas reduz blast radius.

Um problema em desenvolvimento não deve comprometer produção. Uma conta de segurança pode centralizar logs e auditoria.

---

## Organizational Units

Contas podem ser agrupadas em unidades organizacionais.

Exemplo:


* Root: Produção.
* Desenvolvimento: Segurança.
* Logs: Sandbox.


---

## SCPs

Com [[Service Control Policies (SCPs)]], a organização define limites máximos de permissão para contas ou unidades.

---

## Relação com Segurança

Organizations é base para governança em ambientes profissionais.

Ele permite separar responsabilidades, aplicar controles centrais e reduzir risco entre ambientes.

---

## Relação com Gestão Financeira

* [[Faturamento Consolidado da AWS]];
* [[AWS Control Tower]];

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
---

## Relação com AWS CAF

Este conceito também aparece em discussões de adoção de nuvem dentro do [[AWS Cloud Adoption Framework (AWS CAF)]], especialmente quando a organização precisa criar governança, plataforma e operação consistentes para usar AWS em escala.

---

## Pontos que Costumam Gerar Confusão

Quando o cenário envolve consolidar e gerenciar várias contas AWS em um local central, a resposta é [[AWS Organizations]].

---

## Como entender

Organizations permite criar e organizar contas, aplicar políticas, usar faturamento consolidado e estruturar governança multi-conta.

---

## Cuidado importante na prática

IAM gerencia identidades e permissões.

Organizations gerencia múltiplas contas AWS.

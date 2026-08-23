Service Control Policies, ou SCPs, são políticas do [[AWS Organizations]] que definem limites máximos de permissão para contas.

Elas não concedem acesso diretamente. Elas limitam o que pode ser permitido dentro de uma conta.

Em Service Control Policies (SCPs), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Service Control Policies (SCPs) deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

---

## Por que existe

Service Control Policies (SCPs) existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Como Funcionam**

Se uma SCP nega uma ação, nenhuma identidade da conta pode executá-la, mesmo que uma política [[AWS Identity and Access Management (IAM)|IAM]] local permita.

---

## Exemplo prático

Uma organização pode usar SCP para impedir que qualquer conta desative [[AWS CloudTrail]] ou crie recursos fora de regiões aprovadas.

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

Não confunda controles de segurança diferentes. [[AWS Identity and Access Management (IAM)|IAM]] decide permissões, KMS protege chaves, CloudTrail registra ações, GuardDuty detecta comportamento suspeito, WAF filtra tráfego de aplicação e Shield atua contra DDoS.

---

## Cuidados

SCP mal configurada pode bloquear operações legítimas.

Deve ser aplicada com testes e estratégia clara.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Relação com outras notas

**Relação com [[AWS Identity and Access Management (IAM)|IAM]]**

[[Políticas IAM]] controlam permissões dentro da conta.

SCPs controlam o limite organizacional.

As duas camadas são avaliadas em conjunto.

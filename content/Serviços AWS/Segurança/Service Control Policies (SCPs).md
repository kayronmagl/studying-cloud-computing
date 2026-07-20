Service Control Policies, ou SCPs, são políticas do [[AWS Organizations]] que definem limites máximos de permissão para contas.

Elas não concedem acesso diretamente. Elas limitam o que pode ser permitido dentro de uma conta.

---

## Visão geral

Em Service Control Policies (SCPs), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Como Funcionam

Se uma SCP nega uma ação, nenhuma identidade da conta pode executá-la, mesmo que uma política IAM local permita.

---

## Exemplo

Uma organização pode usar SCP para impedir que qualquer conta desative [[AWS CloudTrail]] ou crie recursos fora de regiões aprovadas.

---

## Relação com IAM

[[Políticas IAM]] controlam permissões dentro da conta.

SCPs controlam o limite organizacional.

As duas camadas são avaliadas em conjunto.

---

## Cuidado

SCP mal configurada pode bloquear operações legítimas.

Deve ser aplicada com testes e estratégia clara.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

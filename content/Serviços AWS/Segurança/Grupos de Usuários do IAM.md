Grupos de Usuários do [[AWS Identity and Access Management (IAM)|IAM]] são coleções de [[Usuários do IAM]] usadas para facilitar administração de permissões.

Em vez de anexar políticas manualmente a cada usuário, cria-se um grupo e anexa-se a política ao grupo.

Em Grupos de Usuários do [[AWS Identity and Access Management (IAM)|IAM]], pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Grupos de Usuários do IAM deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Grupos de Usuários do [[AWS Identity and Access Management (IAM)|IAM]] existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**O que Grupos Não São**

Grupos não são identidades assumíveis.

Uma aplicação não “assume um grupo”. Quem pode ser assumida é uma [[Roles do IAM|role]].

Grupos servem para organizar usuários.

---

## Exemplo prático

* Grupo: Desenvolvedores: pode visualizar logs.
* pode acessar ambiente de desenvolvimento
* Grupo: Operadores: pode reiniciar serviços.
* pode consultar métricas
* Grupo: Auditores: pode ler CloudTrail.
* não pode alterar recursos

Usuários herdariam as permissões dos grupos aos quais pertencem.

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

**Boas Práticas**

* agrupar por função;
* evitar grupos genéricos demais;
* não anexar permissões administrativas sem necessidade;
* revisar membros periodicamente;
* aplicar [[Princípio do Menor Privilégio]].

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com Políticas**

Grupos recebem [[Políticas IAM]].

A política define o que membros do grupo podem fazer.

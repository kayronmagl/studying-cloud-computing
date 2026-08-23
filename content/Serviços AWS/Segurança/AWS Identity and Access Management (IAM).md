AWS Identity and Access Management, ou IAM, é o serviço da AWS responsável por controlar identidade e autorização.

IAM define quem pode fazer o quê, em qual recurso e sob quais condições.

Ele é uma das peças mais importantes da AWS porque quase toda ação na conta passa por autorização: criar uma instância, ler um [[Buckets S3|bucket]], apagar um banco, publicar um evento, consultar logs ou assumir uma role.

Em AWS Identity and Access Management (IAM), pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

IAM controla identidade e permissões na AWS.

Ele responde: quem pode fazer o quê, em qual recurso e sob quais condições.

---

## Por que existe

AWS Identity and Access Management (IAM) existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Componentes Principais**

IAM trabalha com:

* [[Usuários do IAM]];
* [[Grupos de Usuários do IAM]];
* [[Roles do IAM]];
* [[Políticas IAM]];
* [[AWS Security Token Service (STS)]];
* [[Autenticação Multifator (MFA)]];
* [[Princípio do Menor Privilégio]];
* [[Permission Boundaries]];
* [[Credenciais Temporárias]];
* [[Credenciais de Longo Prazo]];
* [[Access Keys]].

**Identidade vs Permissão**

Identidade responde:

* quem é?

Permissão responde:

* o que pode fazer?

Uma identidade sem política não tem permissão útil. Uma política sem identidade ou recurso não produz acesso prático.

**Avaliação de Políticas**

Quando uma solicitação chega, a AWS avalia políticas aplicáveis.

Em alto nível:

* negação explícita: vence tudo.
* permissão explícita: permite se não houver negação.
* ausência de permissão: nega por padrão.

Esse modelo é essencial: na AWS, o padrão seguro é negar.

**Usuários vs Roles**

[[Usuários do IAM]] representam identidades diretas, normalmente pessoas ou integrações legadas.

[[Roles do IAM]] são identidades assumíveis, normalmente usadas por serviços, aplicações, automações e acesso temporário.

Em arquiteturas modernas, roles são preferíveis para workloads porque evitam credenciais permanentes.

**Elementos**

* Usuário IAM: identidade individual.
* Grupo: conjunto de usuários.
* Role: identidade assumível por serviços, contas ou usuários.
* Política: documento JSON que permite ou nega ações.
* MFA: segunda camada de autenticação.
* STS: emite credenciais temporárias.

**Princípio Fundamental**

Use o [[Princípio do Menor Privilégio]]: conceda somente o necessário.

---

## Exemplo prático

Uma função [[AWS Lambda]] precisa ler objetos de um [[Buckets S3|bucket]] [[Amazon S3]].

A função não deve receber credenciais fixas. Ela deve usar uma role com permissão mínima para ler apenas o [[Buckets S3|bucket]] necessário.

Isso aplica o [[Princípio do Menor Privilégio]].

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

Não confunda controles de segurança diferentes. IAM decide permissões, KMS protege chaves, CloudTrail registra ações, GuardDuty detecta comportamento suspeito, WAF filtra tráfego de aplicação e Shield atua contra DDoS.

---

## Cuidados

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Role não é usuário. Role é assumida temporariamente. Serviços como [[Amazon EC2|EC2]] e [[AWS Lambda|Lambda]] devem usar roles, não access keys fixas.

---

## Relação com outras notas

- [[Usuários do IAM]]
- [[Grupos de Usuários do IAM]]
- [[Roles do IAM]]
- [[Políticas IAM]]
- [[AWS Security Token Service (STS)]]
- [[Autenticação Multifator (MFA)]]
- [[Princípio do Menor Privilégio]]
- [[Permission Boundaries]]
- [[Credenciais Temporárias]]
- [[Credenciais de Longo Prazo]]

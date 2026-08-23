Políticas [[AWS Identity and Access Management (IAM)|IAM]] são documentos que definem permissões na AWS.

Elas especificam se uma ação é permitida ou negada, em quais recursos e sob quais condições.

Políticas normalmente são escritas em JSON.

Em Políticas [[AWS Identity and Access Management (IAM)|IAM]], pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Políticas IAM deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

---

## Por que existe

Políticas [[AWS Identity and Access Management (IAM)|IAM]] existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**Estrutura Conceitual**

Uma política possui elementos como:

* Effect;
* Action;
* Resource;
* Condition;
* Principal, em políticas baseadas em recurso.

Exemplo conceitual:

```json
{
  "Effect": "Allow",
  "Action": "s3: GetObject",
  "Resource": "arn:aws:s3:::meu-bucket/*"
}
```

**Allow e Deny**

`Allow` concede permissão.

`Deny` nega permissão.

Uma negação explícita tem prioridade sobre permissões.

**Tipos**

Políticas podem ser:

* [[Políticas Baseadas em Identidade]];
* [[Políticas Baseadas em Recurso]];
* policies gerenciadas pela AWS;
* policies gerenciadas pelo cliente;
* inline policies;
* permission boundaries;
* [[Service Control Policies (SCPs)]].

**Resource**

O campo Resource limita onde a ação pode ocorrer.

Permitir `s3: GetObject` em todos os [[Buckets S3|buckets]] é muito diferente de permitir apenas em um [[Buckets S3|bucket]] específico.

**Condition**

Condições refinam acesso.

Exemplos:

* permitir apenas com MFA;
* permitir apenas de certo IP;
* permitir apenas com TLS;
* permitir apenas com tag específica;
* permitir apenas em determinada região.

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

---

## Cuidados

**Erro Comum**

Usar `Action: "*"` e `Resource: "*"` por conveniência.

Isso cria permissões amplas demais e viola o [[Princípio do Menor Privilégio]].

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

- [[Políticas Baseadas em Identidade]]
- [[Políticas Baseadas em Recurso]]
- [[Service Control Policies (SCPs)]]
- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]
- [[Princípio do Menor Privilégio]]

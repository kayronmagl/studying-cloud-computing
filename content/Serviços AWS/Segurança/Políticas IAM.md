Políticas IAM são documentos que definem permissões na AWS.

Elas especificam se uma ação é permitida ou negada, em quais recursos e sob quais condições.

Políticas normalmente são escritas em JSON.

---

## Visão geral

Em Políticas IAM, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Estrutura Conceitual

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

---

## Allow e Deny

`Allow` concede permissão.

`Deny` nega permissão.

Uma negação explícita tem prioridade sobre permissões.

---

## Tipos

Políticas podem ser:

* [[Políticas Baseadas em Identidade]];
* [[Políticas Baseadas em Recurso]];
* policies gerenciadas pela AWS;
* policies gerenciadas pelo cliente;
* inline policies;
* permission boundaries;
* [[Service Control Policies (SCPs)]].

---

## Resource

O campo Resource limita onde a ação pode ocorrer.

Permitir `s3: GetObject` em todos os buckets é muito diferente de permitir apenas em um bucket específico.

---

## Condition

Condições refinam acesso.

Exemplos:

* permitir apenas com MFA;
* permitir apenas de certo IP;
* permitir apenas com TLS;
* permitir apenas com tag específica;
* permitir apenas em determinada região.

---

## Erro Comum

Usar `Action: "*"` e `Resource: "*"` por conveniência.

Isso cria permissões amplas demais e viola o [[Princípio do Menor Privilégio]].

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

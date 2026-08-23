Permission Boundaries são limites máximos de permissão aplicados a identidades [[AWS Identity and Access Management (IAM)|IAM]].

Elas não concedem permissão sozinhas. Elas definem o máximo que uma identidade pode receber.

Em Permission Boundaries, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Permission Boundaries deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

---

## Por que existe

Permission Boundaries existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

Uma identidade precisa ter uma política permitindo a ação.

Além disso, a permission boundary precisa permitir que essa ação esteja dentro do limite.

Se a política permite, mas a boundary não permite, a ação é negada.

**Uso**

Permission boundaries são úteis quando equipes podem criar roles ou usuários, mas a organização quer limitar o máximo de permissão possível.

---

## Exemplo prático

Uma equipe de desenvolvimento pode criar roles para aplicações, mas a boundary impede que essas roles concedam acesso administrativo global.

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Diferenças importantes

Não confunda controles de segurança diferentes. [[AWS Identity and Access Management (IAM)|IAM]] decide permissões, KMS protege chaves, CloudTrail registra ações, GuardDuty detecta comportamento suspeito, WAF filtra tráfego de aplicação e Shield atua contra DDoS.

---

## Cuidados

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

---

## Relação com outras notas

**Relação com Governança**

Permission boundaries ajudam a delegar administração sem perder controle central.

- [[AWS WAF]]
- [[AWS Shield]]
- [[AWS Identity and Access Management (IAM)]]
- [[AWS Key Management Service (KMS)]]
- [[AWS CloudTrail]]

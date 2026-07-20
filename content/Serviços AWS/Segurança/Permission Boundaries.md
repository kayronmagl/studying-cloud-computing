Permission Boundaries são limites máximos de permissão aplicados a identidades IAM.

Elas não concedem permissão sozinhas. Elas definem o máximo que uma identidade pode receber.

---

## Visão geral

Em Permission Boundaries, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Como Funciona

Uma identidade precisa ter uma política permitindo a ação.

Além disso, a permission boundary precisa permitir que essa ação esteja dentro do limite.

Se a política permite, mas a boundary não permite, a ação é negada.

---

## Uso

Permission boundaries são úteis quando equipes podem criar roles ou usuários, mas a organização quer limitar o máximo de permissão possível.

---

## Exemplo

Uma equipe de desenvolvimento pode criar roles para aplicações, mas a boundary impede que essas roles concedam acesso administrativo global.

---

## Relação com Governança

Permission boundaries ajudam a delegar administração sem perder controle central.

---

## Exemplo Prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

---

## Cuidados importantes

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Amazon GuardDuty é o serviço de detecção de ameaças da AWS.

Ele analisa sinais como eventos, logs e padrões de atividade para identificar comportamento suspeito.


Em Amazon GuardDuty, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## O que Detecta

GuardDuty pode identificar indícios como:

* chamadas de API incomuns;
* comportamento anômalo;
* possível exfiltração;
* credenciais comprometidas;
* comunicação com domínios maliciosos;
* atividade suspeita em workloads e contas.

---

## Papel

GuardDuty não é firewall.

Ele é detecção.

Seu papel é avisar que algo parece errado para que a equipe investigue e responda.

---

## Relação com Outros Serviços

GuardDuty complementa:

* [[AWS CloudTrail]];
* VPC Flow Logs;
* DNS logs;
* [[AWS Security Hub]];
* resposta automatizada.

---

## Cuidado

Achados precisam de processo.

Sem triagem, priorização e resposta, detecção vira ruído.

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

## Pontos que Costumam Gerar Confusão

GuardDuty é descrito como serviço que realiza detecção inteligente de ameaças na infraestrutura e nos recursos da AWS.

---

## Como entender

GuardDuty analisa sinais como eventos de CloudTrail, logs de VPC, DNS e outros dados compatíveis para identificar comportamento suspeito.

---

## Não confundir

* [[AWS Shield]]: proteção DDoS.
* [[AWS WAF]]: filtra requisições web.
* [[Amazon Inspector]]: vulnerabilidades.
* Amazon GuardDuty: detecção inteligente de ameaças.


---

## Explicação principal

GuardDuty é como um vigia inteligente olhando sinais de ameaça dentro da sua conta AWS.

Ele não substitui firewall, IAM ou boas práticas. Ele ajuda a perceber comportamento suspeito.

---

## Exemplo

Imagine que uma chave de acesso começa a ser usada de um lugar incomum, em horários estranhos, tentando acessar recursos sensíveis.

GuardDuty pode gerar um alerta dizendo que aquilo parece suspeito.

---

## Como reconhecer em perguntas na prática

A frase mais importante é:


* detecção inteligente de ameaças


Se aparecer isso, pense em Amazon GuardDuty.

---

## Diferença para conceitos parecidos

* GuardDuty: detecta ameaças.
* Inspector: procura vulnerabilidades.
* [[AWS WAF|WAF]]: filtra tráfego web.
* Shield: protege contra DDoS.
* [[AWS CloudTrail|CloudTrail]]: registra chamadas de API.


Quando o cenário envolve ameaça inteligente, não escolha WAF nem Shield.

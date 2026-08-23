Amazon GuardDuty é o serviço de detecção de ameaças da AWS.

Ele analisa sinais como eventos, logs e padrões de atividade para identificar comportamento suspeito.

Em Amazon GuardDuty, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.

---

## O que é

Amazon GuardDuty deve ser entendido como controle de confiança. Segurança em nuvem envolve identidade, autenticação, autorização, criptografia, auditoria, isolamento e resposta a incidentes.

Segurança combina [[AWS Identity and Access Management (IAM)|IAM]], rede, criptografia, auditoria, detecção e proteção de aplicação.

GuardDuty analisa sinais como eventos de CloudTrail, logs de [[Amazon VPC|VPC]], DNS e outros dados compatíveis para identificar comportamento suspeito.

GuardDuty é como um vigia inteligente olhando sinais de ameaça dentro da sua conta AWS.

Ele não substitui firewall, [[AWS Identity and Access Management (IAM)|IAM]] ou boas práticas. Ele ajuda a perceber comportamento suspeito.

---

## Por que existe

Amazon GuardDuty existe para reduzir risco de acesso indevido, exposição de dados, abuso de permissões e falta de rastreabilidade. Em nuvem, segurança depende de identidade, configuração, criptografia, auditoria e resposta a incidentes trabalhando juntas.

---

## Como funciona

**O que Detecta**

GuardDuty pode identificar indícios como:

* chamadas de [[APIs|API]] incomuns;
* comportamento anômalo;
* possível exfiltração;
* credenciais comprometidas;
* comunicação com domínios maliciosos;
* atividade suspeita em workloads e contas.

**Papel**

GuardDuty não é firewall.

Ele é detecção.

Seu papel é avisar que algo parece errado para que a equipe investigue e responda.

**Não confundir**

* [[AWS Shield]]: proteção DDoS.
* [[AWS WAF]]: filtra requisições web.
* [[Amazon Inspector]]: vulnerabilidades.
* Amazon GuardDuty: detecção inteligente de ameaças.

**Como reconhecer em perguntas na prática**

A frase mais importante é:

* detecção inteligente de ameaças

Se aparecer isso, pense em Amazon GuardDuty.

---

## Exemplo prático

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Essas camadas reduzem risco de exposição, abuso e alteração indevida.

Imagine que uma chave de acesso começa a ser usada de um lugar incomum, em horários estranhos, tentando acessar recursos sensíveis.

GuardDuty pode gerar um alerta dizendo que aquilo parece suspeito.

---

## Diferenças importantes

**Como Diferenciar**

* [[AWS Identity and Access Management (IAM)|IAM]] controla permissões.
* KMS gerencia chaves.
* WAF filtra HTTP/HTTPS.
* Shield protege contra DDoS.
* CloudTrail audita chamadas de [[APIs|API]].
* GuardDuty detecta ameaças.

**Pontos que Costumam Gerar Confusão**

GuardDuty é descrito como serviço que realiza detecção inteligente de ameaças na infraestrutura e nos recursos da AWS.

**Diferença para conceitos parecidos**

* GuardDuty: detecta ameaças.
* Inspector: procura vulnerabilidades.
* [[AWS WAF|WAF]]: filtra tráfego web.
* Shield: protege contra DDoS.
* [[AWS CloudTrail|CloudTrail]]: registra chamadas de API.

Quando o cenário envolve ameaça inteligente, não escolha WAF nem Shield.

---

## Cuidados

Achados precisam de processo.

Sem triagem, priorização e resposta, detecção vira ruído.

O erro comum é confundir “serviço seguro” com “configuração segura”.

A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Permissão demais é risco. Aplique menor privilégio e use roles temporárias sempre que possível.

---

## Relação com outras notas

**Relação com Outros Serviços**

GuardDuty complementa:

* [[AWS CloudTrail]];
* [[Amazon VPC|VPC]] Flow Logs;
* DNS logs;
* [[AWS Security Hub]];
* resposta automatizada.

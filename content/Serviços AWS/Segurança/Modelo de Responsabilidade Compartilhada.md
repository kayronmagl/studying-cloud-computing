O Modelo de Responsabilidade Compartilhada define a divisão de responsabilidades entre AWS e cliente.

A AWS é responsável pela segurança da nuvem. O cliente é responsável pela segurança na nuvem.

Essa distinção é a base para entender segurança em qualquer serviço AWS.

---

## Visão geral

Em Modelo de Responsabilidade Compartilhada, pense em proteção por camadas. Segurança na AWS combina identidade, rede, criptografia, logs, detecção e resposta.


---

## Segurança da Nuvem

A AWS protege a infraestrutura que executa os serviços:

* data centers;
* hardware físico;
* energia;
* refrigeração;
* rede global;
* virtualização;
* infraestrutura base;
* serviços gerenciados.

O cliente não gerencia racks, switches físicos, controles biométricos ou a camada física da região.

---

## Segurança na Nuvem

O cliente protege o que cria e configura:

* dados;
* identidades;
* permissões;
* sistemas operacionais em [[Amazon EC2]];
* regras de rede;
* criptografia;
* buckets [[Amazon S3]];
* bancos;
* aplicações;
* logs;
* chaves;
* segredos.

---

## Varia Conforme o Serviço

Quanto mais gerenciado o serviço, menos camadas o cliente opera diretamente.

Em [[Amazon EC2]], o cliente gerencia sistema operacional, patches e firewall da instância.

Em [[AWS Lambda]], o cliente não gerencia o servidor, mas ainda gerencia código, permissões, variáveis, segredos, eventos e dados.

Em [[Amazon S3]], o cliente não gerencia disco físico, mas gerencia políticas, acesso público, criptografia e lifecycle.

---

## Exemplo

Se uma aplicação é invadida por falha de código, isso é responsabilidade do cliente.

Se um bucket é tornado público sem necessidade, isso é responsabilidade do cliente.

Se um data center físico falha, isso está no domínio operacional da AWS.

Esse modelo impede terceirizar mentalmente toda a segurança para o provedor.

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

---

## Pontos que Costumam Gerar Confusão

A AWS é responsável pela segurança da nuvem:

* infraestrutura física;
* data centers;
* hardware;
* rede física;
* infraestrutura de virtualização;
* dispositivos de infraestrutura da AWS.

O cliente é responsável pela segurança na nuvem:

* usuários e grupos IAM;
* security groups;
* dados;
* aplicações;
* sistema operacional convidado em EC2;
* treinamento interno de funcionários;
* configuração de recursos.

---

## Ideia Central

* AWS protege a nuvem.
* Cliente protege o que coloca na nuvem.


---

## Cuidado importante na prática

A AWS não configura seus security groups por você.

A AWS não cria seus usuários IAM por você.

A AWS não treina os funcionários da sua empresa.

---

## Proteção em vários níveis

[[Segurança em Camadas]] ajuda a entender por que segurança envolve datacenter, rede, identidade, aplicação e dados.

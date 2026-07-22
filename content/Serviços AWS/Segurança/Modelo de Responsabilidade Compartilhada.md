O Modelo de Responsabilidade Compartilhada define como as responsabilidades de segurança são divididas entre AWS e cliente. A ideia central é simples, mas precisa ser entendida com cuidado: a AWS protege a infraestrutura da nuvem; o cliente protege o que cria, configura e executa na nuvem.

Essa distinção evita uma confusão perigosa. Usar um serviço da AWS não significa terceirizar toda a segurança. O provedor opera determinadas camadas, mas o cliente continua tomando decisões sobre dados, permissões, rede, aplicações, logs, chaves, segredos e configuração.

## Segurança da Nuvem

Segurança da nuvem é a parte que fica sob responsabilidade da AWS. Ela inclui data centers, hardware físico, energia, refrigeração, rede global, infraestrutura de virtualização e a base que sustenta os serviços.

O cliente não gerencia racks, switches físicos, controles biométricos ou a camada física da região. Quando um data center físico precisa de proteção, energia redundante ou substituição de hardware, isso está no domínio operacional da AWS.

## Segurança na Nuvem

Segurança na nuvem é a parte que fica sob responsabilidade do cliente. Ela inclui dados, identidades, permissões, regras de rede, criptografia, aplicações, logs, chaves, segredos e configurações.

Em [[Amazon EC2]], por exemplo, o cliente gerencia sistema operacional, patches, firewall da instância, aplicação e permissões. Em [[AWS Lambda]], o cliente não gerencia o servidor, mas ainda gerencia código, permissões, variáveis, segredos, eventos e dados. Em [[Amazon S3]], o cliente não gerencia disco físico, mas gerencia políticas, acesso público, criptografia e ciclo de vida dos objetos.

Quanto mais gerenciado o serviço, menos camadas o cliente opera diretamente. Isso reduz trabalho operacional, mas não elimina responsabilidade.

## Exemplo

Se uma aplicação é invadida por falha no código, isso está no lado do cliente. Se um bucket S3 é tornado público sem necessidade, isso também é responsabilidade do cliente. Se um data center físico falha, a operação da infraestrutura está no domínio da AWS.

Esse exemplo mostra por que o modelo é chamado de compartilhado. A segurança final depende das duas partes. A AWS pode proteger a infraestrutura e, ainda assim, uma configuração incorreta do cliente pode expor dados.

## Controles

Uma aplicação pública pode usar [[AWS WAF]] para filtrar requisições, [[AWS Shield]] para proteção contra DDoS, [[AWS Identity and Access Management (IAM)|IAM]] para permissões, [[AWS Key Management Service (KMS)|KMS]] para chaves e [[AWS CloudTrail]] para auditoria.

Esses controles reduzem riscos diferentes. IAM controla quem pode fazer o quê. KMS protege chaves criptográficas. WAF filtra tráfego HTTP e HTTPS. CloudTrail registra chamadas de API. Juntos, eles ajudam a montar [[Segurança em Camadas]], combinando proteção de identidade, rede, aplicação, dados e auditoria.

## Erros Comuns

O erro mais comum é confundir “serviço seguro” com “configuração segura”. A AWS protege a infraestrutura, mas o cliente ainda precisa configurar identidade, rede, dados, logs e aplicação corretamente.

Outro erro é conceder permissões amplas para facilitar testes e esquecer de reduzi-las depois. Permissão demais aumenta o impacto de erro, vazamento ou abuso. O [[Princípio do Menor Privilégio]] deve orientar usuários, roles, aplicações e automações.

Também é incorreto imaginar que a AWS cria automaticamente security groups corretos, usuários IAM adequados, políticas de backup, criptografia, treinamento interno ou resposta a incidente. Essas decisões continuam exigindo arquitetura, operação e governança do lado do cliente.

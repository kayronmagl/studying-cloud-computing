Servidores físicos são máquinas reais, instaladas em racks, com CPU, memória, discos, interfaces de rede, energia e refrigeração. Eles executam sistemas operacionais, aplicações, bancos de dados e plataformas de virtualização.

## Exemplo Prático

Antes da nuvem se popularizar, muitas organizações precisavam comprar servidores, esperar entrega, instalar em data centers, configurar rede, energia, armazenamento e sistema operacional. Se a demanda crescesse, era necessário adquirir mais equipamentos. Se a demanda caísse, parte da capacidade ficava parada.

Na nuvem, o usuário normalmente não gerencia o servidor físico diretamente. Ele consome abstrações como máquinas virtuais, contêineres, funções ou serviços gerenciados. Em [[Amazon EC2]], por exemplo, a instância parece um servidor para o usuário, mas ela é executada sobre infraestrutura física controlada pela AWS.

---

## Cuidados importantes

Abstrair o servidor físico não significa que ele desapareceu. Toda nuvem continua dependendo de hardware real, energia, rede, refrigeração e manutenção. A diferença está em quem opera essa camada e em quanto dela aparece para o cliente.

---

## Exemplo

Uma aplicação pode rodar em várias instâncias virtuais distribuídas em zonas diferentes. Para a equipe da aplicação, o foco está em sistema operacional, deploy, segurança, escala e monitoramento. A troca de uma peça física, a energia do rack e parte da redundância do data center ficam sob responsabilidade do provedor.

Esse contraste ajuda a entender o modelo de responsabilidade compartilhada: a nuvem reduz a operação física do cliente, mas não elimina decisões sobre arquitetura, permissões, dados, configuração e disponibilidade.

---

## Erros Comuns

Um erro comum é pensar que usar nuvem significa não usar servidores. O servidor pode não estar visível para o cliente, mas continua existindo na infraestrutura do provedor. Esse ponto é importante para entender virtualização, [[Bare-metal]], disponibilidade e falhas físicas.

## Servidor físico direto

[[Bare-metal]] ajuda a entender o contraste entre administrar hardware diretamente e consumir capacidade pela nuvem.

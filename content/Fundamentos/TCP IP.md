TCP/IP é o conjunto de protocolos que sustenta a comunicação da [[Internet Pública]].

O nome combina dois protocolos centrais: TCP (*Transmission Control Protocol*) e IP (*Internet Protocol*). O IP cuida de endereçamento e roteamento. O TCP cuida de entrega confiável entre aplicações.

## IP

O IP permite que máquinas tenham endereços e que pacotes sejam encaminhados entre redes.

Em nuvem, isso aparece em [[Amazon VPC]], [[Subnets]], [[Route Tables]], [[Internet Gateway]] e comunicação entre serviços.

---

## TCP

O TCP cria uma conexão confiável.

Ele controla ordem, retransmissão, perda e fluxo.

Quando uma aplicação acessa uma API HTTPS da AWS, TCP normalmente está abaixo da camada TLS e HTTP.

---

## Relação com Nuvem

Sem TCP/IP, não haveria acesso ao [[AWS Management Console]], chamadas para [[APIs]], comunicação com [[Amazon EC2]], envio de objetos para [[Amazon S3]] ou tráfego entre aplicações distribuídas.

---

## Relação com Modelo OSI

O [[Modelo OSI]] é um modelo conceitual.

TCP/IP é a pilha prática usada na internet.

Entender essa diferença ajuda a diagnosticar problemas de rede: IP, rota, porta, DNS, firewall, TLS, aplicação e permissão são camadas diferentes do problema.

---

## Exemplo Prático

Imagine uma aplicação web simples. Ela precisa receber requisições, processar dados, gravar informações, proteger acesso e responder ao usuário.

Mesmo usando AWS, a aplicação ainda depende de conceitos como rede, protocolo, servidor, banco, API e armazenamento. A diferença é que muitos desses elementos deixam de ser comprados e instalados manualmente e passam a ser configurados por serviço.

---

## Cuidados importantes

O erro comum é decorar o nome do serviço sem entender o fundamento. Isso gera confusão, por exemplo, ao comparar banco relacional com NoSQL, servidor físico com instância virtual, ou API com interface gráfica.

Por isso, esta nota deve funcionar como camada de apoio para entender os módulos posteriores.

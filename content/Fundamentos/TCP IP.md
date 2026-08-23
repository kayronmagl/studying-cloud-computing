TCP/IP é o conjunto de protocolos que sustenta a comunicação da [[Internet Pública]].

O nome combina dois protocolos centrais: TCP (*Transmission Control Protocol*) e IP (*Internet Protocol*). O IP cuida de endereçamento e roteamento. O TCP cuida de entrega confiável entre aplicações.

---

## O que é

TCP IP deve ser entendido como base para interpretar a nuvem. Fundamentos explicam o que já existia antes dos provedores e continua aparecendo em serviços modernos.

---

## Por que existe

TCP IP existe porque nuvem não substitui os fundamentos de computação. Ela reorganiza infraestrutura, rede, dados, segurança e operação em serviços consumíveis.

---

## Como funciona

**IP**

O IP permite que máquinas tenham endereços e que pacotes sejam encaminhados entre redes.

Em nuvem, isso aparece em [[Amazon VPC]], [[Subnets]], [[Route Tables]], [[Internet Gateway]] e comunicação entre serviços.

**TCP**

O TCP cria uma conexão confiável.

Ele controla ordem, retransmissão, perda e fluxo.

Quando uma aplicação acessa uma [[APIs|API]] HTTPS da AWS, TCP normalmente está abaixo da camada TLS e HTTP.

---

## Exemplo prático

Quando uma aplicação chama uma [[APIs|API]] HTTPS, o endereço precisa ser resolvido, os pacotes precisam encontrar uma rota até o destino, uma conexão precisa ser estabelecida e os dados precisam chegar em ordem suficiente para a aplicação interpretar a resposta. O usuário enxerga uma chamada simples, mas por baixo existe uma sequência de decisões de rede.

Em uma arquitetura de nuvem, isso vale tanto para tráfego público quanto para comunicação privada entre serviços. Uma instância pode acessar outra por endereço privado, uma aplicação pode chamar um endpoint de serviço e um usuário pode acessar um sistema pela internet pública. Em todos os casos, endereçamento, roteamento, portas e protocolos continuam determinando se a comunicação funciona.

---

## Diferenças importantes

Compare TCP IP com serviços específicos da AWS. Fundamento explica a ideia geral; serviço é uma implementação concreta dessa ideia dentro de um provedor.

---

## Cuidados

Um erro comum é explicar conectividade apenas pelo nome do serviço de nuvem. Se uma aplicação não responde, o problema pode estar no DNS, na rota, na porta, na regra de firewall, na negociação TLS, na aplicação ou na permissão do serviço. TCP/IP ajuda a separar essas hipóteses antes de alterar a arquitetura sem direção.

---

## Relação com outras notas

**Relação com Nuvem**

Sem TCP/IP, não haveria acesso ao [[AWS Management Console]], chamadas para [[APIs]], comunicação com [[Amazon EC2]], envio de objetos para [[Amazon S3]] ou tráfego entre aplicações distribuídas.

**Relação com Modelo OSI**

O [[Modelo OSI]] é um modelo conceitual.

TCP/IP é a pilha prática usada na internet.

Entender essa diferença ajuda a diagnosticar problemas de rede: IP, rota, porta, DNS, firewall, TLS, aplicação e permissão são camadas diferentes do problema.

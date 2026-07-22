Network Address Translation, ou NAT, é a técnica de traduzir endereços IP durante a passagem do tráfego por um dispositivo ou serviço de rede.

Na AWS, o caso mais comum é o [[NAT Gateway]], usado para permitir que recursos em subnets privadas acessem a internet sem receber conexões iniciadas externamente.


Network Address Translation (NAT) faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Ideia

Um recurso privado usa IP interno.

Ao sair para a internet por NAT, o tráfego parece partir do endereço público associado ao NAT.

A resposta volta para o NAT, que encaminha ao recurso interno correto.

---

## Uso

NAT é usado para:

* saída de instâncias privadas;
* atualizações de sistema;
* acesso a APIs públicas;
* downloads;
* integrações externas.

---

## Cuidado

NAT não é firewall completo.

Ele controla direção de conexão, mas regras de segurança, rotas, IAM, logs e monitoramento continuam necessários.

---

## Exemplo Prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e VPC Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Cuidados importantes

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

---

## Como entender isso

Este conceito pertence ao módulo de redes na AWS.

## Ponto central

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

## Como Diferenciar

* VPC é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

## Cuidado importante

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

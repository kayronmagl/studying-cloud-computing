DNS TTL significa Time To Live em registros DNS.

Ele define por quanto tempo uma resposta DNS pode permanecer em cache antes de ser consultada novamente.


DNS TTL faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Exemplo

Um TTL de 300 segundos permite que resolvers mantenham a resposta por até 5 minutos.

TTL baixo facilita mudanças rápidas. TTL alto reduz consultas e melhora cache.

---

## Relação com Route 53

No [[Amazon Route 53]], TTL influencia migração, failover, cutover e propagação de mudanças.

---

## Cuidado

Mesmo com TTL baixo, alguns resolvers e clientes podem se comportar de forma diferente.

Planeje mudanças críticas com antecedência.

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

## Exemplo aplicado

TTL influencia quanto tempo uma resposta DNS fica em cache.

Se o TTL é alto, clientes e resolvedores demoram mais para buscar uma nova resposta. Isso reduz consultas, mas torna mudanças mais lentas.

Se o TTL é baixo, alterações se propagam mais rápido, mas podem gerar mais consultas DNS. Em arquiteturas com failover ou mudança frequente de destino, esse detalhe pode afetar o tempo percebido de recuperação.

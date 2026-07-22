AWS Client VPN permite que usuários remotos acessem recursos dentro da AWS por meio de uma VPN gerenciada.

Diferente de [[AWS Site-to-Site VPN]], que conecta redes, Client VPN conecta usuários individuais.


AWS Client VPN faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Uso

* acesso remoto de administradores;
* acesso seguro a subnets privadas;
* equipes distribuídas;
* substituição de VPN corporativa autogerenciada;
* acesso temporário a ambientes internos.

---

## Relação com VPC

O usuário se conecta ao endpoint Client VPN e pode acessar recursos dentro da [[Amazon VPC]], conforme rotas, autorização e regras de segurança.

---

## Cuidado

Client VPN não substitui IAM, Security Groups ou auditoria.

Ela apenas fornece caminho de rede. Permissões e controles de aplicação continuam necessários.

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

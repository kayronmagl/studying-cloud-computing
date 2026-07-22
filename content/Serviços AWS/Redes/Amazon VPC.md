Amazon VPC, ou Amazon Virtual Private Cloud, é o serviço que permite criar uma rede virtual isolada dentro da AWS. Essa rede se parece conceitualmente com uma rede que uma organização manteria em um data center próprio, mas é criada por software e integrada aos serviços da nuvem.

Uma VPC responde a uma pergunta básica de arquitetura: onde os recursos ficam e por quais caminhos eles podem se comunicar? Em nuvem, rede não significa apenas “ter internet”. Ela envolve isolamento, endereçamento, subnets, rotas, DNS, gateways, regras de segurança e conectividade com outros ambientes.

## Como Funciona

Uma VPC define um espaço de rede dentro de uma [[Regions (Regiões)|região]]. Dentro desse espaço, o usuário define [[Blocos CIDR]], cria [[Subnets]], associa [[Route Tables]], configura gateways e controla tráfego com [[Security Groups]] e [[Network ACLs]].

A VPC é regional, mas suas subnets pertencem a [[Availability Zones (AZ)]] específicas. Essa diferença é importante para disponibilidade. Uma aplicação distribuída entre duas AZs normalmente precisa de subnets em cada zona, para que load balancers, instâncias e bancos possam ser posicionados corretamente.

## Subnets e Rotas

Uma subnet não é pública apenas pelo nome. Ela se torna pública quando possui rota adequada para um [[Internet Gateway]] e quando os recursos têm configuração que permite conectividade pública, como endereço IP público quando necessário.

Subnets privadas não recebem acesso direto da internet. Recursos nelas podem iniciar conexões externas por meio de um [[NAT Gateway]], mas não precisam aceitar conexões vindas diretamente da internet. Esse padrão é comum para instâncias de aplicação, bancos e serviços internos.

As route tables determinam o caminho do tráfego. Se uma rota está errada ou ausente, recursos que parecem corretamente criados podem não conseguir se comunicar. Por isso, ao desenhar uma VPC, a pergunta prática deve ser: quem precisa falar com quem, por qual caminho e com qual permissão?

## Segurança

[[Security Groups]] atuam no nível do recurso, como uma instância EC2. Eles são stateful: uma resposta ao tráfego permitido é automaticamente considerada parte da comunicação. [[Network ACLs]] atuam no nível da subnet e são stateless, ou seja, regras de ida e volta precisam ser consideradas separadamente.

Essa diferença ajuda a evitar configurações confusas. Security group e NACL não são controles idênticos em camadas diferentes. Eles têm comportamentos diferentes e devem ser usados de forma complementar.

## Exemplo

Uma VPC de produção pode usar um bloco como `10.0.0.0/16` e dividi-lo em subnets públicas e privadas em mais de uma AZ. Um load balancer pode ficar em subnets públicas, enquanto instâncias e bancos ficam em subnets privadas. O NAT Gateway permite saída controlada para atualizações ou chamadas externas. [[VPC Endpoints]] permitem acessar determinados serviços AWS sem passar pela internet pública.

Esse desenho melhora segmentação e pode contribuir para alta disponibilidade, mas também introduz custo e complexidade. NAT Gateway, tráfego entre zonas, endpoints e transferência de dados precisam ser considerados no desenho.

## Conectividade

Uma VPC também pode se conectar a outras redes. Isso pode envolver peering, VPN, [[AWS Direct Connect]], [[AWS Transit Gateway]] ou endpoints privados. Em ambientes híbridos, a VPC se torna a ponte entre recursos na AWS e sistemas mantidos fora da nuvem.

Dentro da VPC, [[Endereços IP Privados]] identificam recursos internamente sem expô-los diretamente à internet. Para investigação, [[VPC Flow Logs]] ajudam a analisar metadados de tráfego aceito ou rejeitado.

## Erros Comuns

Um erro comum é colocar recursos em subnets públicas sem necessidade. Isso aumenta superfície de exposição. Outro erro é criar subnets privadas sem rota de saída quando os recursos precisam baixar atualizações ou chamar APIs externas.

Também é comum planejar mal o CIDR. Mudar endereçamento depois pode ser difícil, principalmente quando existem várias VPCs, VPNs, Direct Connect ou redes externas que não podem ter sobreposição de endereços.

Rede mal desenhada pode causar exposição indevida, falta de conectividade entre serviços e custo inesperado de tráfego. Por isso, VPC precisa ser estudada junto com segurança, disponibilidade e precificação.

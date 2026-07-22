On-premise é o modelo em que a infraestrutura é mantida localmente pela organização ou por uma instalação dedicada sob seu controle. Servidores, armazenamento, rede, energia, refrigeração, espaço físico, manutenção e segurança física precisam ser planejados diretamente.

Dentro dos [[Modelos de Implantação em Nuvem]], on-premise representa o cenário em que a organização mantém controle direto sobre a infraestrutura física. A nuvem muda parte dessa lógica ao trocar compra e operação direta de hardware por consumo de serviços, muitas vezes associado a [[OpEx (Operating Expenses)]] e [[Pay-as-you-go]].

## Como Funciona

Em um ambiente on-premise, a capacidade precisa existir antes de ser usada. Se uma aplicação precisa de mais processamento, armazenamento ou rede, a organização depende da capacidade já instalada ou precisa adquirir, instalar e configurar novos recursos.

Esse modelo pode usar virtualização, automação e ferramentas modernas de operação. Mesmo assim, a base física continua sob responsabilidade da organização. Alguém precisa cuidar de ciclo de vida de hardware, substituição de peças, energia, refrigeração, cabeamento, segurança física, backups, recuperação e atualização dos ambientes.

## Diferença para Nuvem

A diferença entre on-premise e nuvem não está nos conceitos fundamentais. Uma aplicação continua precisando receber requisições, processar dados, gravar informações, proteger acesso e responder ao usuário. Ela ainda depende de rede, protocolo, servidor, banco, API e armazenamento.

O que muda é a forma de obter e operar esses elementos. Em on-premise, muitos recursos são comprados, instalados e mantidos diretamente. Na nuvem, eles passam a ser provisionados por serviços, políticas e APIs sobre infraestrutura operada por um provedor.

## Exemplo

Imagine uma aplicação web simples mantida localmente. Ela pode ter servidores em um rack da empresa, um banco de dados em outro servidor, equipamentos de rede conectando tudo e uma equipe responsável por backups, energia, atualizações e segurança física.

Se a demanda crescer, talvez seja necessário comprar novos servidores ou aumentar a capacidade existente. Se um equipamento falhar, a recuperação depende das peças, contratos, redundância e processos disponíveis naquele ambiente. Esse controle direto pode ser uma vantagem em alguns cenários, mas também aumenta a responsabilidade operacional.

## Quando Faz Sentido

On-premise pode ser adequado quando há exigência forte de controle físico, dependência de sistemas legados, integração com equipamentos locais, cargas muito previsíveis ou infraestrutura já amortizada.

Pode ser inadequado quando a organização precisa criar ambientes rapidamente, escalar com frequência, operar globalmente ou reduzir a responsabilidade direta sobre data centers. Quando a arquitetura combina recursos locais com recursos em nuvem, o assunto deixa de ser apenas on-premise e passa a envolver implantação híbrida.

## Erros Comuns

Um erro comum é tratar on-premise como tecnologia ultrapassada por definição. O modelo pode continuar adequado dependendo de requisitos técnicos, financeiros, regulatórios e operacionais.

Outro erro é imaginar que nuvem elimina os fundamentos. Mesmo usando AWS, Azure ou Google Cloud, a aplicação continua dependendo de computação, rede, armazenamento, banco de dados, segurança e operação. A diferença está em quem administra cada camada e como os recursos são consumidos.

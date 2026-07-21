Modelos de implantação em nuvem descrevem onde os recursos de tecnologia são executados, quem controla a infraestrutura física e como os ambientes são conectados e operados.

Essa diferença parece simples, mas afeta quase todas as decisões de arquitetura. O lugar onde servidores, redes, bancos e sistemas de armazenamento são executados muda a forma de provisionar recursos, controlar acesso, estimar custos, lidar com falhas, escalar aplicações e cumprir requisitos regulatórios.

Modelos de implantação não são a mesma coisa que modelos de serviço. Modelos de serviço, como infraestrutura como serviço (Infrastructure as a Service, IaaS), plataforma como serviço (Platform as a Service, PaaS) e software como serviço (Software as a Service, SaaS), explicam qual camada é entregue pelo provedor e quais responsabilidades continuam com o cliente. Modelos de implantação explicam onde e sob qual responsabilidade essa infraestrutura ou serviço funciona.

---

## Implantação baseada em nuvem

Na implantação baseada em nuvem, os recursos principais de computação, armazenamento, banco de dados e rede são executados na infraestrutura de um [[Provedores de Nuvem|provedor de nuvem]]. Servidores virtuais, serviços de aplicação, bancos gerenciados, filas, buckets, balanceadores de carga e redes lógicas são criados sobre [[Data Centers|data centers]] operados pelo provedor.

O cliente não possui os prédios, racks, servidores físicos, energia, refrigeração e conectividade física que sustentam o serviço. Essa camada fica com o provedor. Mesmo assim, o cliente continua responsável por decisões dentro do ambiente: arquitetura, dados, permissões, configurações, redes lógicas, monitoramento, custos e aplicações.

O provisionamento costuma ocorrer por interfaces como console web, [[APIs]], [[AWS CLI]], [[AWS SDKs]] e [[Computação em Nuvem/Interação com AWS/Infraestrutura como Código (IaC)|Infraestrutura como Código]]. Isso permite criar e alterar recursos com rapidez, mas também exige controle para evitar exposição indevida, recursos esquecidos e custos inesperados. A nuvem reduz a necessidade de comprar infraestrutura física, mas não elimina responsabilidade operacional. Dependendo do serviço usado, o cliente ainda precisa configurar identidade, rede, criptografia, backup, observabilidade, atualização de sistemas, políticas de acesso e desenho de recuperação.

A conectividade pode usar a [[Internet Pública]], mas não se limita a ela. Recursos privados podem se comunicar por redes internas do provedor, [[VPC Endpoints]], [[AWS PrivateLink]] ou outros mecanismos de conectividade privada, conforme a arquitetura. Estar na nuvem não significa que todos os componentes ficam expostos publicamente. Uma aplicação pode ter apenas um balanceador acessível pelos usuários e manter instâncias, bancos e serviços internos em sub-redes privadas.

Uma aplicação web simples nesse modelo poderia receber tráfego em um [[Elastic Load Balancing|load balancer]], processar requisições em instâncias ou serviços de computação, armazenar arquivos no [[Amazon S3]], persistir dados estruturados no [[Amazon RDS]] e isolar seus componentes em uma [[Amazon VPC]]. Todos esses recursos continuam tendo mecanismos técnicos reais, mas a compra, instalação e manutenção física da base são abstraídas pelo provedor.

Uma organização pode usar esse modelo de mais de uma forma. Ela pode migrar sistemas existentes, criar aplicações nativas de nuvem ou combinar as duas abordagens. Migrar não é apenas transferir arquivos ou servidores. Uma carga pode ser movida com poucas mudanças, como em uma estratégia de rehost; pode receber ajustes para usar serviços gerenciados, como em replatform; pode ser redesenhada para explorar melhor a nuvem, como em refactor; ou pode ser substituída por uma nova aplicação criada diretamente para esse ambiente.

Esse modelo é adequado quando a organização precisa começar rápido, escalar sem comprar hardware antecipadamente, usar serviços gerenciados, testar ideias com menor barreira inicial ou distribuir aplicações em múltiplas regiões. Pode ser inadequado quando há exigências rígidas de controle físico, dependências legadas difíceis de migrar, restrições regulatórias específicas, latência local extrema ou custos previsíveis que favorecem infraestrutura própria bem utilizada. O uso da nuvem também exige disciplina financeira, porque recursos criados sem governança podem continuar gerando custo mesmo quando não entregam valor.

---

## Implantação on-premises

Na implantação [[On-Premise|on-premises]], os recursos são executados em infraestrutura controlada pela própria organização ou por uma instalação contratada para esse fim. Servidores, armazenamento, rede, energia, refrigeração, espaço físico e manutenção precisam ser planejados diretamente.

O provisionamento depende do ambiente local. Pode envolver compra de hardware, instalação de sistema operacional, configuração de virtualização, criação de redes, armazenamento compartilhado e ferramentas internas de automação. Mesmo quando há virtualização e automação, a capacidade física precisa existir antes de ser usada. Virtualização melhora o aproveitamento de servidores e facilita a criação de máquinas virtuais, mas, sozinha, não transforma um ambiente local em computação em nuvem. Para se aproximar do modelo de nuvem, seria necessário oferecer autosserviço, elasticidade, medição de uso, provisionamento automatizado e operação padronizada em cima da infraestrutura.

A escalabilidade tende a ser mais lenta porque depende de capacidade já disponível ou de aquisição adicional. Expandir pode exigir compra, entrega, instalação, cabeamento, configuração e homologação de novos equipamentos. A vantagem é maior controle sobre localização física, integração com sistemas legados, políticas internas e requisitos específicos de operação. A desvantagem é assumir mais responsabilidade por disponibilidade, substituição de equipamentos, energia, refrigeração, segurança física, backup, recuperação e atualização contínua.

O custo costuma ter mais relação com [[CapEx (Capital Expenditures)]], porque a organização compra ou reserva capacidade antes do consumo real. Isso pode ser eficiente quando a carga é estável e previsível, mas pode gerar ociosidade quando a demanda varia muito.

Esse modelo é adequado para sistemas que precisam permanecer próximos a equipamentos locais, cargas estáveis com infraestrutura já amortizada, ambientes com controle físico obrigatório ou dependências legadas fortes. Também pode fazer sentido quando requisitos de soberania de dados, normas internas, integração com maquinário local ou aplicações antigas tornam a migração difícil.

Não é correto dizer que on-premises sempre tem menor latência. A latência depende de onde estão usuários, sistemas, dados e dependências externas. Um sistema local pode responder muito rápido para equipamentos dentro da mesma instalação, mas ser pior para usuários distantes. Da mesma forma, uma aplicação em nuvem pode ter baixa latência para usuários próximos da região usada e latência maior para sistemas que continuam no datacenter local.

Esse modelo pode ser inadequado quando a organização precisa escalar rapidamente, reduzir compra antecipada de hardware, operar globalmente ou experimentar novos ambientes com frequência. A nota [[On-Premise]] aprofunda a responsabilidade específica da infraestrutura mantida localmente; aqui o foco é comparar esse modelo com outras formas de implantação.

---

## Implantação híbrida

Na implantação híbrida, parte dos recursos permanece on-premises e parte é executada em nuvem. O ponto central não é apenas usar os dois ambientes, mas integrá-los de forma segura, observável e operacionalmente coerente.

Dois ambientes coexistirem não basta para caracterizar uma arquitetura híbrida. Se uma empresa mantém um sistema local isolado e, separadamente, hospeda um site sem relação técnica em nuvem, há apenas dois ambientes. O modelo se torna híbrido quando existe fluxo entre eles: rede, identidade, dados, segurança, monitoramento, processos operacionais ou dependências de aplicação atravessam a fronteira entre a infraestrutura local e a nuvem.

Uma aplicação pode manter um banco sensível em um datacenter local e executar serviços de análise, backup, recuperação de desastre ou front-end em nuvem. Outra arquitetura pode manter sistemas legados on-premises enquanto novas aplicações usam serviços gerenciados na AWS. Em ambos os casos, a integração depende de rede, identidade, segurança, observabilidade e governança.

A conectividade híbrida pode usar VPN, [[AWS Direct Connect]], [[AWS Site-to-Site VPN]], [[AWS Client VPN]], [[AWS Transit Gateway]] e outros recursos de [[Redes na AWS]]. O desenho precisa considerar latência, largura de banda, criptografia, rotas, redundância, DNS, falhas parciais e custo de transferência de dados. Também precisa considerar consistência de dados, porque parte da informação pode estar localmente e outra parte pode ser processada ou armazenada em nuvem.

O provisionamento fica dividido. Recursos locais seguem processos internos da organização. Recursos em nuvem podem ser criados por console, APIs, CLI, SDKs ou infraestrutura como código. Essa diferença aumenta a necessidade de padronização, inventário, controle de permissões e auditoria.

Um exemplo comum é uma aplicação regulada que mantém registros principais em infraestrutura local, envia dados autorizados para processamento em nuvem e retorna os resultados para sistemas internos. Nesse cenário, identidade, criptografia, auditoria, regras de acesso e rotas precisam funcionar de forma coordenada nos dois lados. Uma falha de conectividade pode não derrubar todos os sistemas, mas pode interromper fluxos que dependem da comunicação entre os ambientes.

O modelo híbrido é adequado quando a organização precisa migrar gradualmente, manter sistemas legados, atender requisitos de residência de dados, integrar ambientes corporativos existentes ou usar a nuvem como expansão de capacidade. Pode ser inadequado quando a equipe não consegue operar dois ambientes com consistência, quando a latência entre eles compromete a aplicação, quando a dependência de conectividade cria fragilidade ou quando a integração gera complexidade maior que o benefício. Híbrido não é automaticamente mais maduro; ele só faz sentido quando a necessidade de integração justifica o custo operacional adicional.

---

## Multicloud não é automaticamente híbrido

Multicloud significa usar serviços de dois ou mais provedores de nuvem. Uma arquitetura pode usar AWS para parte da computação e outro provedor para análise, armazenamento, inteligência artificial ou distribuição global, por exemplo. Isso não exige infraestrutura on-premises.

Híbrido significa integrar nuvem com infraestrutura local, privada ou dedicada fora do provedor de nuvem pública. Por isso, uma arquitetura pode ser somente multicloud, somente híbrida ou as duas coisas ao mesmo tempo.

Um ambiente que usa AWS e outro provedor, sem datacenter local integrado, é multicloud, mas não híbrido. Um ambiente que usa um datacenter próprio conectado à AWS é híbrido, mesmo que use apenas um provedor de nuvem. Um ambiente que usa datacenter local, AWS e outro provedor ao mesmo tempo pode ser híbrido e multicloud.

---

## Comparação prática

Em uma implantação baseada em nuvem, a maior parte da infraestrutura física é responsabilidade do provedor, e o cliente administra recursos lógicos e aplicações. Em uma implantação on-premises, a organização assume desde a base física até as camadas superiores. Em uma implantação híbrida, as responsabilidades são divididas e precisam ser coordenadas entre ambientes.

| Critério | Baseada em nuvem | On-premises | Híbrida |
| --- | --- | --- | --- |
| Local dos recursos | Infraestrutura do provedor de nuvem | Infraestrutura controlada pela organização ou instalação dedicada | Parte local e parte em nuvem |
| Responsabilidade física | Provedor cuida de prédios, energia, hardware e infraestrutura física | Organização assume hardware, energia, refrigeração, espaço e manutenção | Dividida conforme o ambiente |
| Provisionamento | Console, APIs, CLI, SDKs e infraestrutura como código | Processos locais, virtualização, automação interna e capacidade já adquirida | Combinação dos processos locais com os mecanismos da nuvem |
| Elasticidade | Maior capacidade de ajustar recursos sob demanda | Limitada pela capacidade instalada ou comprada | Possível na parte em nuvem, mas condicionada pela integração |
| Conectividade | Pode ser pública, privada ou interna ao provedor | Geralmente local ou corporativa, com saída para redes externas quando necessário | Depende de VPNs, links dedicados, rotas, DNS e políticas entre ambientes |
| Controle | Menor controle físico, maior abstração operacional | Maior controle físico e operacional direto | Controle dividido e mais difícil de padronizar |
| Custo inicial | Menor compra antecipada de hardware | Maior investimento inicial ou reserva de capacidade | Pode combinar investimento local com consumo em nuvem |
| Custo operacional | Varia conforme consumo, dados trafegados e serviços usados | Inclui equipe, manutenção, energia, espaço e ciclo de vida de hardware | Inclui operação dos dois ambientes e custos de conectividade |
| Latência | Depende de região, usuários, arquitetura e serviços usados | Pode ser baixa para sistemas próximos; não é garantia universal | Depende do tráfego entre nuvem e ambiente local |
| Conformidade | Depende de região, contratos, controles e configuração | Pode atender requisitos de controle físico específico | Pode atender transição ou residência de dados, mas aumenta a necessidade de auditoria |
| Complexidade operacional | Reduz parte da operação física, mas exige governança de nuvem | Concentra responsabilidade técnica e física na organização | Normalmente maior, porque integra dois modelos |
| Casos adequados | Escala rápida, experimentação, serviços gerenciados, alcance geográfico | Cargas previsíveis, controle físico, dependência local, legado forte | Migração gradual, integração corporativa, expansão de capacidade, requisitos regulatórios |
| Limites | Custos variáveis, dependência do provedor, governança e configuração incorreta | Escala lenta, ociosidade, ciclo de vida de hardware e operação pesada | Latência, consistência, custo de transferência, conectividade e coordenação operacional |

Essa diferença afeta custo, segurança, disponibilidade e operação. Na nuvem, a elasticidade pode aproximar capacidade da demanda, mas exige governança de consumo. On-premises pode oferecer controle local, mas exige planejamento antecipado de capacidade. Híbrido pode facilitar transição e integração, mas adiciona complexidade de rede, identidade, observabilidade, consistência de dados e resposta a falhas.

Nenhum modelo é universalmente melhor. A escolha depende de requisitos técnicos, financeiros, regulatórios e operacionais. Em muitos cenários reais, a arquitetura combina mais de um modelo ao longo do tempo.

---

## Relação com outros conceitos

Para entender a diferença entre modelo de implantação e operação local, aprofunde em [[On-Premise]].

Para entender como recursos são criados e administrados em nuvem, revise [[Provisionamento]], [[Recursos de Nuvem]], [[AWS Management Console]], [[AWS CLI]], [[AWS SDKs]] e [[Computação em Nuvem/Interação com AWS/Infraestrutura como Código (IaC)|Infraestrutura como Código]].

Para entender conectividade entre ambientes, revise [[Redes na AWS]], [[AWS Direct Connect]], [[AWS Site-to-Site VPN]], [[AWS Client VPN]], [[AWS PrivateLink]] e [[VPC Endpoints]].

Para entender migrações, revise [[Estratégias de Migração para a Nuvem]].

Para entender a divisão de responsabilidades, revise [[Modelo de Responsabilidade Compartilhada]].

Para entender continuidade e recuperação, revise [[Disaster Recovery (DR)]].

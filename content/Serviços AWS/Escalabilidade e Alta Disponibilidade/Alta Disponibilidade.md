Alta disponibilidade é uma propriedade arquitetural que busca manter um serviço acessível mesmo quando componentes falham. Ela parte de uma ideia prática: falhas vão acontecer, então a aplicação precisa ser desenhada para que uma falha isolada não derrube tudo.

Na AWS, alta disponibilidade costuma envolver distribuição entre múltiplas [[Availability Zones (AZ)]], redução de [[Single Points of Failure (SPOF)]], balanceamento de carga, health checks, replicação, monitoramento e mecanismos de recuperação. Esses recursos ajudam, mas não tornam uma aplicação altamente disponível por si só. A disponibilidade real depende de como aplicação, dados, rede, permissões, capacidade e operação foram desenhados.

## Como Funciona

Uma arquitetura altamente disponível evita depender de um único componente essencial. Em vez de uma única instância receber todo o tráfego, a aplicação pode ter várias instâncias. Em vez de uma única zona concentrar todos os recursos, a arquitetura pode distribuir componentes entre AZs. Em vez de enviar tráfego para qualquer destino, um balanceador pode usar health checks para encaminhar requisições apenas para recursos saudáveis.

Esse desenho não impede todas as falhas. O objetivo é reduzir interrupções e limitar o impacto. Mesmo em uma arquitetura bem projetada, podem existir tempo de detecção, tempo de [[Failover]], reconexões, perda de sessão, indisponibilidade parcial, degradação de desempenho e operações que precisam ser repetidas.

## Componentes

Os componentes mais comuns de alta disponibilidade aparecem juntos. Redundância cria alternativas. [[Application Load Balancer|Load balancers]] distribuem tráfego. [[Health Checks]] identificam destinos ruins. [[Auto Scaling Groups]] ajustam ou repõem capacidade. Bancos [[Multi-AZ]] reduzem dependência de uma única zona. Backups, monitoramento, alarmes e testes confirmam se o desenho funciona quando algo falha.

O ponto importante é que nenhum componente isolado resolve tudo. Auto Scaling não garante alta disponibilidade sozinho. Ter múltiplas instâncias sem health check pode manter falhas ativas. Ter várias AZs disponíveis na região não distribui automaticamente todos os recursos. Recursos zonais, subnets, bancos, permissões, rotas e capacidade precisam ser configurados de forma coerente.

## Exemplo

Uma aplicação com uma única instância EC2 tem baixa disponibilidade porque essa instância é um ponto único de falha. Se ela parar, a aplicação para junto.

Um desenho mais disponível pode colocar várias instâncias em múltiplas AZs atrás de um [[Application Load Balancer]], usar [[Auto Scaling Groups]] para repor capacidade e manter um banco configurado com [[Multi-AZ]]. Se uma instância falhar, o balanceador pode parar de enviar tráfego para ela depois que o health check detectar o problema. Se uma AZ ficar indisponível, a aplicação pode continuar atendendo pela outra, desde que exista capacidade suficiente e que os dados estejam acessíveis.

Isso aumenta a disponibilidade, mas não promete funcionamento sem interrupção. Usuários podem precisar reconectar, sessões podem ser perdidas e algumas operações podem precisar ser repetidas.

## Relação com Resiliência

[[Resiliência]] é mais ampla que alta disponibilidade. Ela inclui recuperação, adaptação, tolerância a falhas, operação durante incidentes e capacidade de voltar a um estado saudável.

Alta disponibilidade também não é o mesmo que [[Tolerância a Falhas]]. Alta disponibilidade pode aceitar uma interrupção curta durante detecção e recuperação. Tolerância a falhas busca manter a operação durante falhas específicas previstas no projeto, com impacto mínimo ou imperceptível. A diferença parece pequena no nome, mas muda o nível de exigência da arquitetura.

## Erros Comuns

Um erro comum é assumir que “usar AWS” já resolve disponibilidade. A AWS oferece regiões, AZs, balanceadores, serviços gerenciados e mecanismos de observabilidade, mas o cliente ainda precisa distribuir recursos, remover SPOFs, configurar health checks, testar failover, proteger dados e acompanhar métricas.

Outro erro é escalar sem observar. Mais instâncias podem aumentar custo sem resolver o gargalo real. Se o problema estiver no banco, na rede, em permissões ou em uma dependência externa, aumentar computação pode apenas tornar a falha mais cara.

Uma Amazon Machine Image, ou AMI, é a imagem usada para iniciar uma [[Instância EC2]].

Ela funciona como um ponto de partida para a instância. Dentro dela ficam o sistema operacional, configurações iniciais e, dependendo do caso, softwares já instalados.

---

## O que é

Amazon Machine Image (AMI) deve ser entendido como vocabulário técnico que explica um comportamento real de sistemas. O termo ajuda a nomear algo que acontece em rede, computação, dados, segurança, desempenho ou operação.

---

## Por que existe

Amazon Machine Image (AMI) existe porque sistemas complexos precisam de nomes precisos. Quando o conceito é entendido, fica mais fácil diagnosticar problemas, comparar serviços e escolher arquitetura.

---

## Como funciona

**Como a AMI é usada**

Quando você cria uma instância no [[Amazon EC2]], precisa escolher de onde essa máquina vai nascer. Essa origem é a AMI.

Uma AMI pode ser fornecida pela AWS, criada por terceiros, comprada no [[AWS Marketplace]] ou criada pela própria empresa a partir de uma instância já configurada.

Isso ajuda a padronizar ambientes. Em vez de configurar cada servidor manualmente, a equipe pode criar uma AMI com o sistema, agentes, pacotes e configurações básicas já prontos.

**O que acontece na prática**

Imagine que uma empresa precisa criar dez servidores iguais para uma aplicação.

Se cada servidor for configurado manualmente, o risco de diferença entre eles aumenta. Com uma AMI padronizada, todas as instâncias começam com a mesma base.

Essa base pode incluir sistema operacional, atualizações, agente do [[Amazon CloudWatch]], ferramentas de segurança, configurações de rede e scripts de inicialização.

---

## Exemplo prático

**Exemplo de padronização**

Uma equipe pode criar uma AMI própria depois de configurar uma instância com sistema operacional, agentes de monitoramento, bibliotecas, ferramentas de segurança e padrões internos.

Depois disso, novas instâncias podem nascer a partir dessa imagem, mantendo consistência entre ambientes.

Esse cuidado é importante em produção. Se cada servidor for configurado manualmente, pequenas diferenças podem gerar erros difíceis de investigar. Com uma AMI padronizada, o ambiente fica mais previsível.

Também é comum atualizar AMIs ao longo do tempo para incluir patches de segurança e novas versões de software.

---

## Diferenças importantes

Compare Amazon Machine Image (AMI) com termos vizinhos antes de usar a palavra como resposta. Conceitos parecidos podem atuar em camadas diferentes: aplicação, rede, armazenamento, banco, identidade ou operação.

---

## Cuidados

AMI não é a instância rodando. A AMI é o modelo usado para criar a instância.

Também não é o mesmo que tipo de instância. A AMI define o conteúdo inicial da máquina. O tipo de instância define CPU, memória, rede e capacidade.

Quando a dúvida envolve a imagem usada para iniciar uma instância [[Amazon EC2|EC2]], a AMI é o conceito central. Ela não decide sozinha desempenho, rede ou custo, mas define a base de software que a máquina terá ao nascer.

---

## Relação com outras notas

- [[Instância EC2]]
- [[Amazon EC2]]
- [[AWS Marketplace]]
- [[Amazon CloudWatch]]

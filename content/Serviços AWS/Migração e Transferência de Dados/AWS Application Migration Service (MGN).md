AWS Application Migration Service, ou AWS MGN, migra servidores físicos e virtuais para a AWS por meio de replicação contínua em nível de bloco.

Ele é voltado principalmente a migrações do tipo lift-and-shift, nas quais a aplicação é transferida com poucas mudanças iniciais.

---

## O que é

AWS Application Migration Service (MGN) deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

AWS Application Migration Service (MGN) existe para mover dados, aplicações ou operações para a nuvem com menor risco. Migração sem estratégia pode apenas deslocar problemas antigos para um ambiente novo.

---

## Como funciona

Um agente de replicação envia continuamente os blocos alterados dos discos de origem para uma área temporária na AWS. A equipe pode executar lançamentos de teste sem interromper o ambiente original.

No cutover, o serviço converte e inicia os servidores como instâncias do [[Amazon EC2]]. Como os dados já estavam sendo replicados, a janela de indisponibilidade tende a ser menor.

**Limites do Lift-and-Shift**

MGN move a workload, mas não moderniza automaticamente sua arquitetura. Dependências antigas, dimensionamento inadequado e problemas operacionais também podem ser levados para a nuvem.

Depois da migração, a equipe pode aplicar [[Refatorar|refatoração]], substituir componentes ou adotar serviços gerenciados.

---

## Exemplo prático

Uma empresa pode mover dados primeiro, validar acesso, migrar uma aplicação menos crítica e só depois avançar para sistemas principais. Nesse processo, AWS Application Migration Service (MGN) ajuda a reduzir risco e organizar a transição.

---

## Diferenças importantes

**Quando Usar**

* migrar servidores on-premises;
* transferir máquinas virtuais;
* reduzir mudanças durante a primeira etapa da migração;
* testar a aplicação antes do cutover;
* manter replicação até a mudança definitiva.

**Diferença para Outros Serviços**

* [[AWS Database Migration Service (DMS)|DMS]]: bancos de dados;
* [[AWS DataSync]]: arquivos e sistemas de armazenamento;
* [[AWS Transfer Family]]: transferência por protocolos como SFTP, FTPS e FTP;
* MGN: servidores e aplicações completas.

---

## Cuidados

O erro comum é migrar sem validação de dependências, dados, rede, permissões, desempenho e plano de retorno. Migração precisa ser testada antes de afetar sistemas críticos.

---

## Relação com outras notas

- [[Amazon EC2]]
- [[Refatorar]]
- [[AWS Database Migration Service (DMS)]]
- [[AWS DataSync]]
- [[AWS Transfer Family]]

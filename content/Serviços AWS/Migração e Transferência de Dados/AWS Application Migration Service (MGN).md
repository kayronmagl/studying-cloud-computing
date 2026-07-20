AWS Application Migration Service, ou AWS MGN, migra servidores físicos e virtuais para a AWS por meio de replicação contínua em nível de bloco.

Ele é voltado principalmente a migrações do tipo lift-and-shift, nas quais a aplicação é transferida com poucas mudanças iniciais.

---

## Como Funciona

Um agente de replicação envia continuamente os blocos alterados dos discos de origem para uma área temporária na AWS. A equipe pode executar lançamentos de teste sem interromper o ambiente original.

No cutover, o serviço converte e inicia os servidores como instâncias do [[Amazon EC2]]. Como os dados já estavam sendo replicados, a janela de indisponibilidade tende a ser menor.

---

## Quando Usar

* migrar servidores on-premises;
* transferir máquinas virtuais;
* reduzir mudanças durante a primeira etapa da migração;
* testar a aplicação antes do cutover;
* manter replicação até a mudança definitiva.

---

## Limites do Lift-and-Shift

MGN move a workload, mas não moderniza automaticamente sua arquitetura. Dependências antigas, dimensionamento inadequado e problemas operacionais também podem ser levados para a nuvem.

Depois da migração, a equipe pode aplicar [[Refatorar|refatoração]], substituir componentes ou adotar serviços gerenciados.

---

## Diferença para Outros Serviços

* [[AWS Database Migration Service (DMS)|DMS]]: bancos de dados;
* [[AWS DataSync]]: arquivos e sistemas de armazenamento;
* [[AWS Transfer Family]]: transferência por protocolos como SFTP, FTPS e FTP;
* MGN: servidores e aplicações completas.

AWS Database Migration Service, ou AWS DMS, migra e replica bancos de dados com baixa interrupção.

Ele pode mover dados para a AWS, entre serviços dentro da AWS ou entre mecanismos compatíveis, mantendo a origem disponível durante boa parte do processo.

---

## Como Funciona

Uma tarefa do DMS conecta um endpoint de origem a um endpoint de destino. O serviço pode executar uma carga inicial e, depois, continuar replicando alterações até o momento do cutover.

Em migrações heterogêneas, nas quais o mecanismo muda, a conversão de schema pode exigir ferramentas adicionais e revisão manual.

---

## Quando Usar

* migrar MySQL, PostgreSQL, Oracle, SQL Server e outros mecanismos compatíveis;
* mover um banco local para [[Amazon RDS]] ou [[Amazon Aurora]];
* manter replicação contínua durante uma migração;
* consolidar ou separar bases;
* reduzir a janela de indisponibilidade.

---

## O que o DMS Não Faz

DMS não migra servidores completos. Esse papel pertence ao [[AWS Application Migration Service (MGN)]].

Também não é uma ferramenta genérica para copiar arquivos. Para esse caso, use [[AWS DataSync]] ou [[AWS Transfer Family]], conforme o protocolo e o fluxo desejado.

---

## Exemplo

Uma empresa pode carregar inicialmente um banco PostgreSQL local para o Amazon RDS e manter a replicação das alterações. Depois de validar a aplicação no destino, direciona as conexões para o novo banco e encerra a replicação.

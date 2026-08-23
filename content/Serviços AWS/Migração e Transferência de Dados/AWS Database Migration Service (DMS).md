AWS Database Migration Service, ou AWS DMS, migra e replica bancos de dados com baixa interrupção.

Ele pode mover dados para a AWS, entre serviços dentro da AWS ou entre mecanismos compatíveis, mantendo a origem disponível durante boa parte do processo.

---

## O que é

AWS Database Migration Service (DMS) deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

AWS Database Migration Service (DMS) existe para mover dados, aplicações ou operações para a nuvem com menor risco. Migração sem estratégia pode apenas deslocar problemas antigos para um ambiente novo.

---

## Como funciona

Uma tarefa do DMS conecta um endpoint de origem a um endpoint de destino. O serviço pode executar uma carga inicial e, depois, continuar replicando alterações até o momento do cutover.

Em migrações heterogêneas, nas quais o mecanismo muda, a conversão de schema pode exigir ferramentas adicionais e revisão manual.

**O que o DMS Não Faz**

DMS não migra servidores completos. Esse papel pertence ao [[AWS Application Migration Service (MGN)]].

Também não é uma ferramenta genérica para copiar arquivos. Para esse caso, use [[AWS DataSync]] ou [[AWS Transfer Family]], conforme o protocolo e o fluxo desejado.

---

## Exemplo prático

Uma empresa pode carregar inicialmente um banco PostgreSQL local para o [[Amazon RDS]] e manter a replicação das alterações. Depois de validar a aplicação no destino, direciona as conexões para o novo banco e encerra a replicação.

---

## Diferenças importantes

**Quando Usar**

* migrar MySQL, PostgreSQL, Oracle, SQL Server e outros mecanismos compatíveis;
* mover um banco local para [[Amazon RDS]] ou [[Amazon Aurora]];
* manter replicação contínua durante uma migração;
* consolidar ou separar bases;
* reduzir a janela de indisponibilidade.

---

## Cuidados

O erro comum é migrar sem validação de dependências, dados, rede, permissões, desempenho e plano de retorno. Migração precisa ser testada antes de afetar sistemas críticos.

---

## Relação com outras notas

- [[AWS Application Migration Service (MGN)]]
- [[AWS DataSync]]
- [[AWS Transfer Family]]
- [[Amazon RDS]]
- [[Amazon Aurora]]

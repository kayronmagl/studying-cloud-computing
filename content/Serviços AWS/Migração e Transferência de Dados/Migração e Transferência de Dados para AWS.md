Migrar para a AWS pode significar mover servidores, bancos de dados, arquivos ou aplicações inteiras. O serviço adequado depende do tipo de origem, do destino, do volume, da conectividade e do quanto a arquitetura será modificada.

---

## O que é

Migração e Transferência de Dados para AWS deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

Migração e Transferência de Dados para AWS existe para mover dados, aplicações ou operações para a nuvem com menor risco. Migração sem estratégia pode apenas deslocar problemas antigos para um ambiente novo.

---

## Como funciona

**Primeiro: Defina o que Está Sendo Movido**

Para servidores físicos ou virtuais, o [[AWS Application Migration Service (MGN)]] replica a workload e facilita testes e cutover.

Para bancos, o [[AWS Database Migration Service (DMS)]] realiza carga inicial e replicação contínua. Mudanças de mecanismo podem exigir conversão de schema e validação adicional.

Para arquivos e sistemas de armazenamento, o [[AWS DataSync]] automatiza transferências online. Quando parceiros ou sistemas legados precisam continuar usando SFTP, FTPS, FTP ou AS2, o [[AWS Transfer Family]] fornece endpoints gerenciados.

**Estratégia de Aplicação**

As [[Estratégias de Migração para a Nuvem]] ajudam a decidir se uma aplicação será mantida, retirada, realocada, recomprada, parcialmente ajustada ou redesenhada.

[[Refatorar]] representa uma mudança mais profunda: componentes são modificados para aproveitar serviços gerenciados, automação, elasticidade e outros padrões nativos de nuvem.

**Transferência Offline e Contexto Histórico**

A [[AWS Snow Family]] reuniu dispositivos físicos como [[AWS Snowcone]], [[AWS Snowball]], [[AWS Snowball Edge]] e [[AWS Snowmobile]]. Atualmente, nenhum deles está disponível para novos clientes. Snowcone e Snowmobile foram encerrados, e Snowball Edge ficou restrito a clientes existentes.

Novos projetos que precisam de transferência física devem avaliar o AWS Data Transfer Terminal ou soluções de parceiros. Transferências online podem combinar DataSync, [[AWS Direct Connect]] e planejamento em lotes.

---

## Exemplo prático

Uma empresa pode mover dados primeiro, validar acesso, migrar uma aplicação menos crítica e só depois avançar para sistemas principais. Nesse processo, Migração e Transferência de Dados para AWS ajuda a reduzir risco e organizar a transição.

---

## Diferenças importantes

**Como Escolher**

Pergunte:

* é um servidor, banco ou conjunto de arquivos?
* a transferência será única ou recorrente?
* existe largura de banda suficiente?
* a aplicação será apenas movida ou redesenhada?
* quanto tempo de indisponibilidade é aceitável?
* como será feita a validação e a reversão?

A [[Comparação de Serviços de Migração e Transferência]] organiza essas diferenças em uma visão única.

---

## Cuidados

O erro comum é migrar sem validação de dependências, dados, rede, permissões, desempenho e plano de retorno. Migração precisa ser testada antes de afetar sistemas críticos.

---

## Relação com outras notas

- [[AWS Application Migration Service (MGN)]]
- [[AWS Database Migration Service (DMS)]]
- [[AWS DataSync]]
- [[AWS Transfer Family]]
- [[Estratégias de Migração para a Nuvem]]
- [[Refatorar]]
- [[AWS Snow Family]]
- [[AWS Snowcone]]
- [[AWS Snowball]]
- [[AWS Snowball Edge]]

AWS Snowcone foi o menor dispositivo da [[AWS Snow Family]]. Ele foi criado para coletar, processar e transferir dados em locais remotos ou com pouca conectividade.

---

## O que é

AWS Snowcone deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

**Situação Atual**

O serviço AWS Snowcone foi descontinuado em 12 de novembro de 2024. Depois dessa data, novos pedidos deixaram de ser aceitos, e o suporte aos dispositivos existentes foi mantido apenas durante o período de encerramento definido pela AWS.

A nota deve ser lida como registro histórico. Para novos projetos, a escolha depende do problema:

* transferência online: [[AWS DataSync]];
* transferência física segura: AWS Data Transfer Terminal ou parceiros;
* computação em local remoto: AWS Outposts ou soluções específicas de edge.

---

## Como funciona

**Como Funcionava**

O dispositivo podia receber dados localmente e depois ser enviado fisicamente à AWS. Também era possível usar o [[AWS DataSync]] para transferir dados pela rede quando havia conectividade suficiente.

Seu tamanho reduzido o tornava adequado para veículos, fábricas, postos remotos, equipes de campo e outros ambientes nos quais um equipamento maior seria difícil de transportar.

---

## Exemplo prático

Uma empresa pode mover dados primeiro, validar acesso, migrar uma aplicação menos crítica e só depois avançar para sistemas principais. Nesse processo, AWS Snowcone ajuda a reduzir risco e organizar a transição.

---

## Diferenças importantes

**Diferença para Outros Dispositivos Snow**

Snowcone era menor e mais portátil que [[AWS Snowball Edge]]. O antigo [[AWS Snowmobile]] atendia uma escala completamente diferente, chegando a até 100 PB por unidade.

---

## Cuidados

O erro comum é migrar sem validação de dependências, dados, rede, permissões, desempenho e plano de retorno. Migração precisa ser testada antes de afetar sistemas críticos.

---

## Relação com outras notas

- [[AWS Snow Family]]
- [[AWS DataSync]]
- [[AWS Snowball Edge]]
- [[AWS Snowmobile]]

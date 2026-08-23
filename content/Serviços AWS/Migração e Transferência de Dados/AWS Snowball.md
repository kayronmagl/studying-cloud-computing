AWS Snowball foi o nome original de uma linha de dispositivos físicos usados para transferir grandes volumes de dados entre ambientes locais e a AWS.

Com a evolução do produto, o nome passou a aparecer principalmente associado ao [[AWS Snowball Edge]], que adicionou capacidade computacional e modelos de armazenamento mais avançados.

---

## O que é

AWS Snowball deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

**Situação Atual**

As gerações antigas de Snowball foram descontinuadas. O [[AWS Snowball Edge]] deixou de aceitar novos clientes em 7 de novembro de 2025.

O termo Snowball ainda é útil para compreender arquiteturas existentes e a história da transferência offline na AWS, mas não deve ser tratado como escolha normal para um projeto novo.

---

## Como funciona

**Problema que Resolvia**

Quando a conexão disponível não conseguia transferir terabytes ou petabytes em uma janela aceitável, o cliente copiava os dados para um dispositivo local e o devolvia à AWS. O conteúdo era então importado, geralmente para [[Amazon S3]].

Esse processo reduzia a dependência da internet, mas exigia logística, planejamento de cópia, criptografia e validação após a importação.

**Alternativas**

Para novos projetos, considere [[AWS DataSync]], [[AWS Direct Connect]], AWS Data Transfer Terminal ou soluções de parceiros, conforme volume, prazo, conectividade e necessidade de transporte físico.

---

## Exemplo prático

Uma empresa pode mover dados primeiro, validar acesso, migrar uma aplicação menos crítica e só depois avançar para sistemas principais. Nesse processo, AWS Snowball ajuda a reduzir risco e organizar a transição.

---

## Diferenças importantes

Não confunda mover para a nuvem com modernizar. Lift-and-shift muda o local de execução; refatoração muda desenho, arquitetura ou uso de serviços nativos.

---

## Cuidados

O erro comum é migrar sem validação de dependências, dados, rede, permissões, desempenho e plano de retorno. Migração precisa ser testada antes de afetar sistemas críticos.

---

## Relação com outras notas

- [[AWS Snowball Edge]]
- [[Amazon S3]]
- [[AWS DataSync]]
- [[AWS Direct Connect]]

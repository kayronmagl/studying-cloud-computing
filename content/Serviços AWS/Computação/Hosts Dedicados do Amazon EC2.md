Hosts Dedicados do Amazon EC2 são servidores físicos dedicados ao uso de um cliente.

Eles aparecem quando uma empresa precisa de isolamento físico, controle de licenciamento ou requisitos específicos de conformidade.

---

## Visão geral

Em uma instância EC2 comum, a AWS fornece isolamento lógico entre clientes. Em alguns cenários, porém, isso não é suficiente para a regra da empresa, licença de software ou exigência de auditoria.

Dedicated Hosts dão mais visibilidade e controle sobre o servidor físico em que as instâncias rodam.

---

## Diferença para modelos de preço

| Opção | Ideia principal |
|---|---|
| On-Demand | Pagar conforme usa |
| Reserved Instances | Desconto por compromisso/reserva |
| Spot Instances | Preço variável com risco de interrupção |
| Dedicated Hosts | Servidor físico dedicado |

---

## Como Diferenciar

Quando o cenário envolve em isolamento físico de instâncias EC2 em relação às instâncias de outros clientes, [[Hosts Dedicados do Amazon EC2]] costuma ser a associação mais direta.

---

## Exemplo aplicado

Um caso comum envolve licenciamento.

Alguns softwares corporativos têm regras ligadas a servidor físico, socket ou núcleo. Se a empresa precisa levar esse software para AWS e manter controle sobre o host físico, Dedicated Hosts podem entrar na arquitetura.

A pista principal continua sendo isolamento físico ou exigência de licenciamento. Se o foco for apenas desconto, a resposta provavelmente está em Reserved Instances ou Savings Plans.

---

## Diferença para outras opções EC2

Dedicated Hosts não são escolhidos porque são simplesmente mais baratos.

Eles entram quando a empresa precisa de servidor físico dedicado, geralmente por licenciamento, auditoria ou conformidade. Isso é diferente de Savings Plans, Reserved Instances e Spot Instances, que são principalmente decisões de preço e capacidade.

Se o enunciado fala em isolamento físico, a pista é Dedicated Hosts. Se fala em compromisso financeiro, a pista muda para Savings Plans ou Reserved Instances.

---

## Exemplo de decisão

Uma empresa pode escolher Dedicated Hosts não porque quer “uma instância maior”, mas porque precisa provar onde a carga roda fisicamente.

Esse detalhe aparece em auditorias, contratos de software e regras de compliance. Se o problema é apenas pagar menos por uso constante, o caminho costuma ser outro: Savings Plans ou Reserved Instances.

---

## Resumo da decisão

A pergunta principal é se existe exigência de host físico dedicado.

Se existir, Dedicated Hosts entram na conversa. Se o problema for apenas reduzir custo, a resposta normalmente estará em Savings Plans, Reserved Instances ou Spot Instances.

Essa separação evita confundir isolamento físico com modelo de desconto.

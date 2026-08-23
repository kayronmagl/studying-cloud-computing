Hosts Dedicados do [[Amazon EC2]] são servidores físicos dedicados ao uso de um cliente.

Eles aparecem quando uma empresa precisa de isolamento físico, controle de licenciamento ou requisitos específicos de conformidade.

Em uma instância [[Amazon EC2|EC2]] comum, a AWS fornece isolamento lógico entre clientes. Em alguns cenários, porém, isso não é suficiente para a regra da empresa, licença de software ou exigência de auditoria.

Dedicated Hosts dão mais visibilidade e controle sobre o servidor físico em que as instâncias rodam.

---

## O que é

Hosts Dedicados do Amazon EC2 deve ser entendido como capacidade de executar trabalho: código, processos, sistemas, containers ou máquinas. Computação na nuvem envolve CPU, memória, imagem, inicialização, rede, permissões, escala e cobrança pelo uso.

---

## Por que existe

Hosts Dedicados do [[Amazon EC2]] existe para explicar uma decisão concreta de computação em nuvem: qual capacidade é necessária, como ela é configurada, quais limites existem e que impacto ela tem em custo, segurança e operação.

---

## Como funciona

**Resumo da decisão**

A pergunta principal é se existe exigência de host físico dedicado.

Se existir, Dedicated Hosts entram na conversa. Se o problema for apenas reduzir custo, a resposta normalmente estará em Savings Plans, Reserved Instances ou Spot Instances.

Essa separação evita confundir isolamento físico com modelo de desconto.

---

## Exemplo prático

Um caso comum envolve licenciamento.

Alguns softwares corporativos têm regras ligadas a servidor físico, socket ou núcleo. Se a empresa precisa levar esse software para AWS e manter controle sobre o host físico, Dedicated Hosts podem entrar na arquitetura.

A pista principal continua sendo isolamento físico ou exigência de licenciamento. Se o foco for apenas desconto, a resposta provavelmente está em Reserved Instances ou Savings Plans.

**Exemplo de decisão**

Uma empresa pode escolher Dedicated Hosts não porque quer “uma instância maior”, mas porque precisa provar onde a carga roda fisicamente.

Esse detalhe aparece em auditorias, contratos de software e regras de compliance. Se o problema é apenas pagar menos por uso constante, o caminho costuma ser outro: Savings Plans ou Reserved Instances.

---

## Diferenças importantes

**Diferença para modelos de preço**

| Opção | Ideia principal |
|---|---|
| On-Demand | Pagar conforme usa |
| Reserved Instances | Desconto por compromisso/reserva |
| Spot Instances | Preço variável com risco de interrupção |
| Dedicated Hosts | Servidor físico dedicado |

**Diferença para outras opções [[Amazon EC2|EC2]]**

Dedicated Hosts não são escolhidos porque são simplesmente mais baratos.

Eles entram quando a empresa precisa de servidor físico dedicado, geralmente por licenciamento, auditoria ou conformidade. Isso é diferente de Savings Plans, Reserved Instances e Spot Instances, que são principalmente decisões de preço e capacidade.

Se o enunciado fala em isolamento físico, a pista é Dedicated Hosts. Se fala em compromisso financeiro, a pista muda para Savings Plans ou Reserved Instances.

---

## Cuidados

O cuidado principal em Hosts Dedicados do [[Amazon EC2]] é usar a opção sem entender dependências. Verifique capacidade, custo, isolamento, permissões, limites e impacto operacional.

---

## Relação com outras notas

- [[O que é computação em nuvem]]

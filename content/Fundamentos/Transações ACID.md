ACID é um conjunto de propriedades que descreve transações confiáveis em bancos de dados.

A sigla significa:

* Atomicidade;
* Consistência;
* Isolamento;
* Durabilidade.

Essas propriedades são fundamentais em [[Bancos de Dados Relacionais]] e em sistemas onde erros de gravação podem corromper regras de negócio.

---

## O que é

Transações ACID deve ser entendido como base para interpretar a nuvem. Fundamentos explicam o que já existia antes dos provedores e continua aparecendo em serviços modernos.

---

## Por que existe

Transações ACID existe porque nuvem não substitui os fundamentos de computação. Ela reorganiza infraestrutura, rede, dados, segurança e operação em serviços consumíveis.

---

## Como funciona

**Atomicidade**

Atomicidade significa que a transação acontece inteira ou não acontece.

Exemplo: em uma compra, não faz sentido debitar pagamento sem criar pedido.

**Consistência**

Consistência significa que a transação leva o banco de um estado válido para outro estado válido.

Regras como chaves, constraints e validações precisam continuar verdadeiras.

**Isolamento**

Isolamento define como transações simultâneas interferem umas nas outras.

Sem isolamento, dois usuários poderiam alterar o mesmo dado de forma inconsistente.

**Durabilidade**

Durabilidade significa que, depois de confirmada, a transação deve sobreviver a falhas.

O dado não pode desaparecer simplesmente porque o servidor reiniciou.

---

## Exemplo prático

Imagine uma compra em uma loja virtual. A aplicação precisa registrar o pedido, reservar ou reduzir o estoque e associar o pagamento à operação. Se o pagamento for confirmado, mas o pedido não for criado, o sistema fica inconsistente. Se o estoque for reduzido, mas a compra falhar, outro cliente pode deixar de comprar um produto disponível.

Uma transação existe para tratar esse conjunto de mudanças como uma unidade lógica. Ou todas as partes necessárias são confirmadas, ou o sistema volta para um estado válido. Esse comportamento é decisivo em domínios como pagamentos, estoque, faturamento, contratos e registros financeiros.

Em um banco relacional, uma transação pode iniciar, alterar várias tabelas e só depois confirmar a gravação. Se uma etapa falhar antes do commit, o banco desfaz as mudanças parciais. Para a aplicação, isso evita que uma sequência de operações deixe registros pela metade.

Na nuvem, serviços como [[Amazon RDS]] e [[Amazon Aurora]] podem reduzir parte da operação do banco, mas não eliminam a necessidade de projetar transações corretamente. A equipe ainda precisa entender isolamento, concorrência, tempo de execução das transações e impacto sobre desempenho.

---

## Diferenças importantes

Compare Transações ACID com serviços específicos da AWS. Fundamento explica a ideia geral; serviço é uma implementação concreta dessa ideia dentro de um provedor.

---

## Cuidados

ACID não significa que qualquer banco relacional será automaticamente rápido, simples ou adequado para qualquer escala. As garantias de transação têm custo em concorrência, bloqueios, replicação, latência e desenho da aplicação. Em sistemas distribuídos, essas decisões ficam ainda mais sensíveis.

**Erros Comuns**

Um erro comum é usar “consistência” de forma genérica. Em ACID, consistência significa preservar regras válidas do banco durante a transação. Isso não é a mesma coisa que consistência eventual em sistemas distribuídos, nem garante por si só que a aplicação modelou corretamente todas as regras de negócio.

---

## Relação com outras notas

**Relação com AWS**

Serviços como [[Amazon RDS]] e [[Amazon Aurora]] são usados quando essas garantias são importantes.

Para modelos NoSQL, algumas garantias podem variar conforme serviço, configuração e padrão de acesso.

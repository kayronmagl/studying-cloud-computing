ACID é um conjunto de propriedades que descreve transações confiáveis em bancos de dados.

A sigla significa:

* Atomicidade;
* Consistência;
* Isolamento;
* Durabilidade.

Essas propriedades são fundamentais em [[Bancos de Dados Relacionais]] e em sistemas onde erros de gravação podem corromper regras de negócio.

## Atomicidade

Atomicidade significa que a transação acontece inteira ou não acontece.

Exemplo: em uma compra, não faz sentido debitar pagamento sem criar pedido.

---

## Consistência

Consistência significa que a transação leva o banco de um estado válido para outro estado válido.

Regras como chaves, constraints e validações precisam continuar verdadeiras.

---

## Isolamento

Isolamento define como transações simultâneas interferem umas nas outras.

Sem isolamento, dois usuários poderiam alterar o mesmo dado de forma inconsistente.

---

## Durabilidade

Durabilidade significa que, depois de confirmada, a transação deve sobreviver a falhas.

O dado não pode desaparecer simplesmente porque o servidor reiniciou.

---

## Relação com AWS

Serviços como [[Amazon RDS]] e [[Amazon Aurora]] são usados quando essas garantias são importantes.

Para modelos NoSQL, algumas garantias podem variar conforme serviço, configuração e padrão de acesso.

---

## Exemplo Prático

Imagine uma aplicação web simples. Ela precisa receber requisições, processar dados, gravar informações, proteger acesso e responder ao usuário.

Mesmo usando AWS, a aplicação ainda depende de conceitos como rede, protocolo, servidor, banco, API e armazenamento. A diferença é que muitos desses elementos deixam de ser comprados e instalados manualmente e passam a ser configurados por serviço.

---

## Cuidados importantes

O erro comum é decorar o nome do serviço sem entender o fundamento. Isso gera confusão, por exemplo, ao comparar banco relacional com NoSQL, servidor físico com instância virtual, ou API com interface gráfica.

Por isso, esta nota deve funcionar como camada de apoio para entender os módulos posteriores.

---

## Exemplo Arquitetural

Em uma aplicação real, o usuário acessa uma interface web, a requisição trafega pela rede, chega a servidores ou funções, consulta bancos e retorna dados. Mesmo que tudo esteja na AWS, os fundamentos continuam existindo.

A diferença é que o provisionamento, a escala, a segurança e a cobrança passam a ser controlados por serviços, políticas e APIs.

---

## Erros Comuns

O erro mais comum é decorar o nome do serviço sem entender o conceito que ele abstrai.

Isso prejudica escolhas como EC2 versus Lambda, RDS versus DynamoDB, S3 versus EBS, ou internet pública versus rede privada.

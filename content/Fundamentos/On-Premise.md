On-Premise é infraestrutura mantida localmente pela organização. Exige compra, instalação, energia, refrigeração e manutenção. A nuvem troca parte disso por [[OpEx (Operating Expenses)]] e [[Pay-as-you-go]].

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

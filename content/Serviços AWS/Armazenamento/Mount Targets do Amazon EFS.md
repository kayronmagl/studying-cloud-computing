Mount Targets do Amazon EFS são endpoints de rede que permitem montar um filesystem [[Amazon EFS]] dentro de uma [[Amazon VPC]].

Cada mount target fica em uma subnet e possui endereço IP. Clientes como instâncias [[Amazon EC2]], containers ou funções precisam alcançar esse endpoint pela rede para montar o filesystem.

## Por que Existem

O EFS é um filesystem de rede.

Para que recursos dentro da VPC acessem esse filesystem, é necessário um ponto de montagem disponível dentro das sub-redes usadas pela aplicação.

---

## Multi-AZ

Em arquiteturas bem desenhadas, cria-se mount target em cada [[Availability Zones (AZ)]] onde existem clientes.

Isso reduz latência e evita que uma instância em uma AZ dependa de mount target em outra AZ.

---

## Segurança

Mount targets usam [[Security Groups]].

A regra típica permite tráfego NFS na porta 2049 apenas a partir dos security groups das aplicações autorizadas.

---

## Exemplo

Uma aplicação com instâncias em duas AZs deve ter:


* AZ A: subnet privada.
* [[Amazon EC2|EC2]]: EFS mount target.
* AZ B: subnet privada.
* [[Amazon EC2|EC2]]: EFS mount target.


Assim, cada instância acessa o EFS por um endpoint local à sua zona.

---

## Exemplo Prático

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Critério de Escolha

Pergunte:


* a aplicação precisa de disco?
* precisa de API de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?


Responder essas perguntas evita usar S3 como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

## Como entender isso

Este conceito pertence ao módulo de armazenamento na AWS.

## Ponto central

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via API, pense em S3. Se for filesystem compartilhado, pense em EFS ou FSx.

## Como Diferenciar

* bloco é diferente de objeto;
* objeto é diferente de arquivo compartilhado;
* classe de armazenamento altera custo e recuperação;
* lifecycle automatiza economia;
* versionamento e backup ajudam recuperação.

## Cuidado importante

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

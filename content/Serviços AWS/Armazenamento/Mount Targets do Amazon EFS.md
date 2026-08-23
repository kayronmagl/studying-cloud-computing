Mount Targets do Amazon EFS são endpoints de rede que permitem montar um filesystem [[Amazon EFS]] dentro de uma [[Amazon VPC]].

Cada mount target fica em uma subnet e possui endereço IP. Clientes como instâncias [[Amazon EC2]], containers ou funções precisam alcançar esse endpoint pela rede para montar o filesystem.

---

## O que é

Mount Targets do Amazon EFS deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Mount Targets do Amazon EFS existe para organizar como dados são guardados, acessados, protegidos, recuperados e cobrados. Em nuvem, armazenamento não é apenas espaço em disco: envolve durabilidade, disponibilidade, performance, classe de uso, ciclo de vida e custo.

---

## Como funciona

**Por que Existem**

O EFS é um filesystem de rede.

Para que recursos dentro da [[Amazon VPC|VPC]] acessem esse filesystem, é necessário um ponto de montagem disponível dentro das sub-redes usadas pela aplicação.

**Multi-AZ**

Em arquiteturas bem desenhadas, cria-se mount target em cada [[Availability Zones (AZ)]] onde existem clientes.

Isso reduz latência e evita que uma instância em uma AZ dependa de mount target em outra AZ.

---

## Exemplo prático

Uma aplicação com instâncias em duas AZs deve ter:

* AZ A: subnet privada.
* [[Amazon EC2|EC2]]: EFS mount target.
* AZ B: subnet privada.
* [[Amazon EC2|EC2]]: EFS mount target.

Assim, cada instância acessa o EFS por um endpoint local à sua zona.

Uma aplicação pode usar:

* [[Amazon EBS]] para disco de uma instância;
* [[Amazon S3]] para objetos e arquivos;
* [[Amazon EFS]] para filesystem compartilhado;
* classes de armazenamento para reduzir custo de dados antigos.

Cada escolha muda o comportamento da aplicação.

---

## Diferenças importantes

**Critério de Escolha**

Pergunte:

* a aplicação precisa de disco?
* precisa de [[APIs|API]] de objeto?
* precisa compartilhar arquivos entre máquinas?
* precisa arquivar por anos?
* precisa recuperar imediatamente?

Responder essas perguntas evita usar [[Amazon S3|S3]] como se fosse disco, EBS como se fosse compartilhado, ou EFS como se fosse banco.

**Como Diferenciar**

* bloco é diferente de objeto;
* objeto é diferente de arquivo compartilhado;
* classe de armazenamento altera custo e recuperação;
* lifecycle automatiza economia;
* versionamento e backup ajudam recuperação.

---

## Cuidados

**Segurança**

Mount targets usam [[Security Groups]].

A regra típica permite tráfego NFS na porta 2049 apenas a partir dos security groups das aplicações autorizadas.

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

---

## Relação com outras notas

- [[Amazon EFS]]
- [[Amazon VPC]]
- [[Amazon EC2]]
- [[Availability Zones (AZ)]]
- [[Amazon EBS]]
- [[Amazon S3]]
- [[Security Groups]]

Classes de Armazenamento do Amazon EFS permitem otimizar custo conforme o padrão de acesso dos arquivos.

Arquivos frequentemente acessados permanecem em camadas de acesso rápido. Arquivos menos acessados podem ser movidos para camadas mais econômicas.

---

## O que é

Classes de Armazenamento do Amazon EFS deve ser entendido pelo tipo de dado que guarda, pelo modo de acesso e pela durabilidade esperada. Em armazenamento na nuvem, a decisão central é separar objeto, bloco, arquivo, backup, ciclo de vida, recuperação e custo.

Uma pergunta principal é: como o dado será acessado?

Se for disco de servidor, pense em EBS. Se for objeto via [[APIs|API]], pense em [[Amazon S3|S3]]. Se for filesystem compartilhado, pense em EFS ou FSx.

---

## Por que existe

Filesystems compartilhados podem acumular dados antigos.

Sem política de ciclo de vida, arquivos frios continuam custando como dados ativos.

---

## Como funciona

**Lifecycle no EFS**

As classes de armazenamento do EFS são mais úteis quando o filesystem acumula dados com diferentes temperaturas de acesso.

Arquivos recentes podem permanecer em classe de acesso frequente. Arquivos antigos podem migrar para classes mais baratas conforme políticas de lifecycle.

---

## Exemplo prático

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

Mover arquivos para classes frias pode afetar latência no primeiro acesso.

O primeiro acesso a dados frios pode ter latência diferente. A aplicação precisa tolerar esse comportamento.

Não escolha armazenamento só pelo nome do serviço. Escolha pelo padrão de acesso.

---

## Relação com outras notas

**Relação com Custo**

Sem lifecycle, um filesystem compartilhado pode crescer durante anos e manter todo dado em uma camada cara.

Com lifecycle, o custo acompanha melhor o uso real.

- [[Amazon EBS]]
- [[Amazon S3]]
- [[Amazon EFS]]

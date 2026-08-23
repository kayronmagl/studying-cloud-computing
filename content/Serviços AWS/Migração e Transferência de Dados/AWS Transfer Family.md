AWS Transfer Family oferece endpoints gerenciados para transferência de arquivos usando protocolos conhecidos, como SFTP, FTPS, FTP e AS2.

Os arquivos podem ser armazenados diretamente no [[Amazon S3]] ou no [[Amazon EFS]], sem que a equipe precise administrar servidores próprios de transferência.

---

## O que é

AWS Transfer Family deve ser entendido pela função que cumpre dentro de uma arquitetura de nuvem. O importante é identificar recurso, dado, rede, permissão, operação e custo envolvidos.

---

## Por que existe

AWS Transfer Family existe para mover dados, aplicações ou operações para a nuvem com menor risco. Migração sem estratégia pode apenas deslocar problemas antigos para um ambiente novo.

---

## Como funciona

O serviço cria um endpoint e integra autenticação, usuários, permissões, logs e armazenamento. Clientes e parceiros continuam usando ferramentas e protocolos já conhecidos, enquanto a infraestrutura é operada pela AWS.

---

## Exemplo prático

Uma empresa pode mover dados primeiro, validar acesso, migrar uma aplicação menos crítica e só depois avançar para sistemas principais. Nesse processo, AWS Transfer Family ajuda a reduzir risco e organizar a transição.

---

## Diferenças importantes

**Quando Usar**

* substituir um servidor SFTP local;
* receber arquivos de parceiros;
* integrar sistemas legados que exigem FTP ou FTPS;
* trocar documentos B2B por AS2;
* enviar os arquivos recebidos diretamente para [[Amazon S3|S3]] ou EFS.

**Diferença para DataSync**

[[AWS DataSync]] é voltado a movimentação automatizada e em grande escala entre sistemas de armazenamento. Transfer Family mantém uma interface baseada em protocolos tradicionais para usuários, aplicações e parceiros.

---

## Cuidados

É necessário definir autenticação, isolamento entre usuários, criptografia, políticas de acesso ao armazenamento e retenção de logs. Um endpoint gerenciado reduz a operação da infraestrutura, mas não elimina a responsabilidade sobre permissões e dados.

---

## Relação com outras notas

- [[Amazon S3]]
- [[Amazon EFS]]
- [[AWS DataSync]]

AWS Transfer Family oferece endpoints gerenciados para transferência de arquivos usando protocolos conhecidos, como SFTP, FTPS, FTP e AS2.

Os arquivos podem ser armazenados diretamente no [[Amazon S3]] ou no [[Amazon EFS]], sem que a equipe precise administrar servidores próprios de transferência.

---

## Como Funciona

O serviço cria um endpoint e integra autenticação, usuários, permissões, logs e armazenamento. Clientes e parceiros continuam usando ferramentas e protocolos já conhecidos, enquanto a infraestrutura é operada pela AWS.

---

## Quando Usar

* substituir um servidor SFTP local;
* receber arquivos de parceiros;
* integrar sistemas legados que exigem FTP ou FTPS;
* trocar documentos B2B por AS2;
* enviar os arquivos recebidos diretamente para S3 ou EFS.

---

## Diferença para DataSync

[[AWS DataSync]] é voltado a movimentação automatizada e em grande escala entre sistemas de armazenamento. Transfer Family mantém uma interface baseada em protocolos tradicionais para usuários, aplicações e parceiros.

---

## Cuidados

É necessário definir autenticação, isolamento entre usuários, criptografia, políticas de acesso ao armazenamento e retenção de logs. Um endpoint gerenciado reduz a operação da infraestrutura, mas não elimina a responsabilidade sobre permissões e dados.

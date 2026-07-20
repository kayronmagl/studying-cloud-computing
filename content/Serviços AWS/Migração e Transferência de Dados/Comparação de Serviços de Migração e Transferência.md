A escolha de uma ferramenta de migração começa pelo tipo de recurso que será movido.

| Necessidade | Serviço ou abordagem | Observação |
|---|---|---|
| Migrar servidores físicos ou virtuais | [[AWS Application Migration Service (MGN)]] | Replicação contínua e lançamento no EC2 |
| Migrar ou replicar bancos | [[AWS Database Migration Service (DMS)]] | Pode combinar carga inicial e replicação de alterações |
| Copiar arquivos e sistemas de armazenamento | [[AWS DataSync]] | Transferência online, automatizada e verificável |
| Manter SFTP, FTPS, FTP ou AS2 | [[AWS Transfer Family]] | Endpoint gerenciado integrado ao S3 ou EFS |
| Transferência física para novos projetos | AWS Data Transfer Terminal ou parceiros | Avaliar disponibilidade regional e capacidade |
| Dispositivos Snow existentes | [[AWS Snowball Edge]] | Restrito a clientes existentes desde novembro de 2025 |
| Conteúdo histórico | [[AWS Snowcone]], [[AWS Snowball]] e [[AWS Snowmobile]] | Serviços ou gerações encerrados |

---

## Diferenças que Mais Importam

MGN trabalha com servidores completos. DMS entende fluxos de banco de dados. DataSync movimenta arquivos e objetos entre sistemas de armazenamento. Transfer Family mantém protocolos tradicionais para usuários e parceiros.

Os antigos dispositivos da [[AWS Snow Family]] resolviam limitações severas de conectividade por meio de transporte físico. Essa família não deve mais ser tratada como opção normal para novos clientes.

---

## Exemplo

Uma empresa pode usar MGN para mover servidores de aplicação, DMS para replicar o banco e DataSync para copiar arquivos compartilhados. Depois dos testes, executa um cutover coordenado e mantém um plano de retorno caso a validação falhe.

O valor da comparação está em separar responsabilidades. Nenhuma ferramenta substitui planejamento de dependências, segurança, testes, observabilidade e validação dos dados.

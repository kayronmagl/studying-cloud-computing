AWS Snowmobile foi um serviço de transferência física criado para migrações em escala extrema. Um contêiner reforçado transportado por caminhão podia receber até 100 PB de dados e depois levá-los a uma região da AWS.

---

## Como Funcionava

O Snowmobile era conectado à rede do cliente e aparecia como um grande datastore. A organização copiava os dados para o contêiner, a AWS transportava a unidade com controles físicos e de segurança, e o conteúdo era importado para [[Amazon S3]].

Esse modelo fazia sentido quando transferir dezenas de petabytes ou exabytes pela rede seria impraticável.

---

## Situação Atual

AWS Snowmobile entrou em desligamento total em 14 de março de 2024. Ele não deve ser apresentado como opção disponível para uma nova arquitetura.

A relação “100 PB por unidade” continua relevante apenas para compreender materiais históricos e questões antigas de certificação.

---

## Alternativas

Novos projetos devem avaliar:

* [[AWS DataSync]] para transferência online automatizada;
* [[AWS Direct Connect]] para conectividade privada e previsível;
* AWS Data Transfer Terminal ou soluções de parceiros para transferência física;
* planejamento em lotes quando o volume puder ser dividido.

[[AWS Snowball Edge]] também aparece em arquiteturas existentes, mas não aceita novos clientes.

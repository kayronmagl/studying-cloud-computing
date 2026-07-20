AWS Snowcone foi o menor dispositivo da [[AWS Snow Family]]. Ele foi criado para coletar, processar e transferir dados em locais remotos ou com pouca conectividade.

---

## Como Funcionava

O dispositivo podia receber dados localmente e depois ser enviado fisicamente à AWS. Também era possível usar o [[AWS DataSync]] para transferir dados pela rede quando havia conectividade suficiente.

Seu tamanho reduzido o tornava adequado para veículos, fábricas, postos remotos, equipes de campo e outros ambientes nos quais um equipamento maior seria difícil de transportar.

---

## Situação Atual

O serviço AWS Snowcone foi descontinuado em 12 de novembro de 2024. Depois dessa data, novos pedidos deixaram de ser aceitos, e o suporte aos dispositivos existentes foi mantido apenas durante o período de encerramento definido pela AWS.

A nota deve ser lida como registro histórico. Para novos projetos, a escolha depende do problema:

* transferência online: [[AWS DataSync]];
* transferência física segura: AWS Data Transfer Terminal ou parceiros;
* computação em local remoto: AWS Outposts ou soluções específicas de edge.

---

## Diferença para Outros Dispositivos Snow

Snowcone era menor e mais portátil que [[AWS Snowball Edge]]. O antigo [[AWS Snowmobile]] atendia uma escala completamente diferente, chegando a até 100 PB por unidade.

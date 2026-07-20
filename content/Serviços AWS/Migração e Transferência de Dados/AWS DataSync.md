AWS DataSync automatiza a transferência online de dados entre ambientes locais, outros provedores, edge locations e serviços de armazenamento da AWS.

Ele é usado principalmente com [[Amazon S3]], [[Amazon EFS]] e Amazon FSx, reduzindo o trabalho de criar scripts próprios para cópia, validação e retomada de transferências.

---

## Como Funciona

Em muitos cenários, um agente é instalado próximo à origem. Ele lê os dados, aplica otimizações de transferência, envia o conteúdo pela rede e verifica se os arquivos chegaram corretamente ao destino.

O serviço permite agendar tarefas, controlar largura de banda, acompanhar métricas e repetir apenas o que não foi transferido.

---

## Quando Usar

* migrar um NAS ou file server para a AWS;
* copiar dados para S3, EFS ou FSx;
* sincronizar arquivos de forma recorrente;
* mover grandes conjuntos de dados sem desenvolver uma ferramenta própria;
* transferir dados entre serviços compatíveis.

---

## Limitações

DataSync depende de conectividade de rede. O prazo real varia conforme largura de banda, latência, quantidade de arquivos e capacidade da origem e do destino.

Ele não migra a estrutura lógica de um banco de dados como o [[AWS Database Migration Service (DMS)]] e não replica servidores inteiros como o [[AWS Application Migration Service (MGN)]].

---

## Exemplo

Uma empresa pode usar DataSync para copiar, durante várias noites, arquivos de um NAS local para [[Amazon S3]]. Depois da carga inicial, tarefas incrementais transferem somente as alterações até o momento da mudança definitiva.

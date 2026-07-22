APIs são interfaces programáveis usadas para que sistemas conversem entre si de forma padronizada. Em vez de uma pessoa clicar em uma tela, um programa envia uma requisição com dados, recebe uma resposta e decide o próximo passo a partir dela.

## Exemplo Prático

Em uma aplicação web simples, o navegador pode chamar uma API para buscar os dados de um produto. A API recebe a requisição, valida se o cliente tem permissão, consulta um banco de dados e devolve uma resposta em um formato que o navegador consegue interpretar.

Na nuvem, esse mesmo princípio aparece em praticamente todas as operações. Quando alguém cria um recurso pelo console web, usa uma CLI, executa um SDK ou aplica Infraestrutura como Código, a ação normalmente chega ao provedor por meio de APIs. Isso permite criar, alterar, consultar e remover [[Recursos de Nuvem]] de maneira repetível, automatizada e auditável.

---

## Cuidados importantes

Uma API não é a mesma coisa que uma interface gráfica. A interface gráfica organiza botões, formulários e telas para uma pessoa operar o sistema. A API organiza entradas, saídas, regras de autenticação, códigos de resposta e formatos de dados para que outro sistema consiga operar de forma automática.

---

## Exemplo

Um script pode pedir ao provedor de nuvem a criação de uma máquina virtual, informar tamanho, imagem do sistema operacional, rede e regras de acesso, e depois receber um identificador do recurso criado. O resultado não depende de uma pessoa repetir cliques manualmente. Depende de uma chamada bem definida, com parâmetros compreensíveis para o serviço.

Essa é a base de automação em nuvem: a infraestrutura deixa de ser apenas algo instalado fisicamente e passa a ser também algo descrito, solicitado e controlado por software.

---

## Erros Comuns

Um erro comum é imaginar que API serve apenas para desenvolvedores de aplicação. Em computação em nuvem, APIs também fazem parte da operação da infraestrutura. Elas permitem provisionar servidores, configurar redes, criar bancos, consultar métricas e aplicar políticas de segurança.

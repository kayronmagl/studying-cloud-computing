Redes de computadores permitem que dispositivos, aplicações e serviços troquem dados. Sem rede, um sistema ficaria isolado: o navegador não alcançaria o servidor, a aplicação não acessaria o banco de dados e os serviços de nuvem não conseguiriam se comunicar entre si.

---

## O que é

Redes de Computadores deve ser entendido como base para interpretar a nuvem. Fundamentos explicam o que já existia antes dos provedores e continua aparecendo em serviços modernos.

---

## Por que existe

Redes de Computadores existe porque nuvem não substitui os fundamentos de computação. Ela reorganiza infraestrutura, rede, dados, segurança e operação em serviços consumíveis.

---

## Como funciona

Redes de Computadores funciona conectando teoria e prática: recurso físico, abstração lógica, software, comunicação, permissão, observação e custo. Essa ligação impede estudar serviços como nomes soltos.

---

## Exemplo prático

Quando uma pessoa acessa uma aplicação web, a requisição precisa sair do dispositivo do usuário, atravessar redes intermediárias, encontrar o endereço correto, chegar ao serviço de entrada da aplicação e ser encaminhada ao componente capaz de responder. Esse caminho depende de endereçamento, roteamento, portas, protocolos e regras de segurança.

Na AWS, esses fundamentos aparecem em serviços e recursos como [[Amazon VPC]], [[Subnets]], [[Route Tables]] e [[Security Groups]]. A nuvem muda a forma de criar e administrar a rede, mas não elimina os conceitos de origem, destino, rota, isolamento, permissão e tráfego.

Em uma arquitetura comum, uma aplicação recebe tráfego público em uma camada de entrada, mas mantém bancos de dados em redes privadas. O usuário consegue acessar o serviço publicado, porém não consegue se conectar diretamente ao banco. Essa separação reduz exposição e ajuda a aplicar o princípio de menor privilégio também na rede.

Entender essa diferença é essencial antes de estudar serviços específicos de rede. Sem o fundamento, termos como sub-rede pública, sub-rede privada, rota, gateway e grupo de segurança viram apenas nomes decorados.

---

## Diferenças importantes

Compare Redes de Computadores com serviços específicos da AWS. Fundamento explica a ideia geral; serviço é uma implementação concreta dessa ideia dentro de um provedor.

---

## Cuidados

Redes não servem apenas para “dar acesso à internet”. Elas também isolam ambientes, limitam o alcance de recursos sensíveis, controlam caminhos de comunicação e influenciam latência, disponibilidade e segurança. Uma aplicação pode estar em nuvem e ainda assim usar conectividade privada entre partes do sistema.

**Erros Comuns**

Um erro comum é confundir conectividade com exposição pública. Um recurso pode se comunicar com outros sistemas sem estar aberto diretamente para a internet, usando rotas privadas, endpoints privados ou conexões dedicadas, conforme a arquitetura.

---

## Relação com outras notas

- [[Amazon VPC]]
- [[Subnets]]
- [[Route Tables]]
- [[Security Groups]]

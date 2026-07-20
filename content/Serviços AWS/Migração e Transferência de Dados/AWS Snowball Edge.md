AWS Snowball Edge é um dispositivo físico que combina transferência offline de dados com capacidade de armazenamento e processamento na borda.

Ele foi usado em migrações de grande volume e em ambientes com conectividade limitada, como fábricas, embarcações, locais remotos e operações temporárias.

---

## Como Funciona

A AWS envia o dispositivo ao cliente. Os dados são copiados pela rede local e o equipamento é devolvido para importação na nuvem. Em cenários de edge computing, aplicações também podem processar dados localmente antes de enviá-los à AWS.

O dispositivo utiliza criptografia, controles de acesso, proteção física e cadeia de custódia para reduzir o risco durante o transporte.

---

## Situação Atual

Desde 7 de novembro de 2025, AWS Snowball Edge não está disponível para novos clientes. Clientes existentes podem continuar usando o serviço conforme as condições e a disponibilidade definidas pela AWS.

Com essa mudança, nenhum dispositivo da [[AWS Snow Family]] pode ser solicitado por novos clientes.

---

## Alternativas para Novos Projetos

* transferência online: [[AWS DataSync]];
* conexão privada de alta capacidade: [[AWS Direct Connect]];
* transferência física segura: AWS Data Transfer Terminal ou soluções de parceiros;
* computação local gerenciada: AWS Outposts.

---

## Diferença para os Outros Nomes

[[AWS Snowcone]] era menor e foi descontinuado. [[AWS Snowmobile]] atendia transferências de até 100 PB e também foi encerrado. [[AWS Snowball]] é o nome histórico mais amplo associado aos dispositivos que antecederam e deram origem às gerações Snowball Edge.

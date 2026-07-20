---
aliases:
  - Serviços AWS/Migração e Transferência de Dados/AWS DeepRacer
---

AWS DeepRacer foi criado para ensinar machine learning por meio de um carro autônomo em escala reduzida e de um simulador de corridas. O foco sempre foi o aprendizado por reforço: o participante define uma função de recompensa, treina o modelo e observa como o agente melhora suas decisões por tentativa e erro.

---

## Como Funcionava

O modelo recebia informações sobre a pista e escolhia ações como acelerar, frear ou virar. A função de recompensa atribuía valores maiores aos comportamentos desejados, por exemplo permanecer na pista, completar uma volta ou manter uma trajetória mais eficiente.

O treinamento acontecia no simulador. Depois, o modelo podia ser avaliado em corridas virtuais ou implantado em um veículo físico compatível.

---

## Situação Atual

Desde 15 de dezembro de 2025, o AWS DeepRacer não existe mais como serviço no Console da AWS. A experiência passou a ser disponibilizada como produto de código aberto, executado dentro da própria conta AWS, e os dispositivos oficiais deixaram de ser vendidos.

O conteúdo continua útil para estudar aprendizado por reforço, funções de recompensa, simulação e avaliação de modelos. O que mudou foi a forma de acesso: não se trata mais de um serviço gerenciado disponível diretamente no console.

---

## O que Não é

DeepRacer não é uma ferramenta de migração, armazenamento ou transferência de dados. Ele não tem relação com dispositivos históricos da [[AWS Snow Family]] ou com o antigo [[AWS Snowmobile]].

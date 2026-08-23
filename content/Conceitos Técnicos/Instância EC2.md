Uma instância [[Amazon EC2|EC2]] é um servidor virtual criado pelo [[Amazon EC2]].

Ela é usada para executar aplicações, serviços, scripts, [[APIs|APIs]], servidores web, workers, bancos autogerenciados ou qualquer workload que precise de uma máquina virtual.

---

## O que é

Instância EC2 deve ser entendido como vocabulário técnico que explica um comportamento real de sistemas. O termo ajuda a nomear algo que acontece em rede, computação, dados, segurança, desempenho ou operação.

---

## Por que existe

Instância [[Amazon EC2|EC2]] existe para explicar uma decisão concreta de computação em nuvem: qual capacidade é necessária, como ela é configurada, quais limites existem e que impacto ela tem em custo, segurança e operação.

---

## Como funciona

**Como a instância nasce**

Quando você cria uma instância, a AWS provisiona capacidade computacional dentro da infraestrutura dela.

Você escolhe uma [[Amazon Machine Image (AMI)]], um tipo de instância, uma rede, uma subnet, regras de segurança, armazenamento e, em muitos casos, uma forma de acesso.

A instância passa a existir dentro de uma [[Amazon VPC]], com endereço IP privado e, se configurado, endereço público.

**O que acontece na prática**

Imagine uma aplicação web simples.

Você pode criar uma instância [[Amazon EC2|EC2]], instalar o servidor da aplicação, abrir as portas necessárias em [[Security Groups]] e anexar um volume [[Amazon EBS]] para armazenamento persistente.

Se a aplicação crescer, talvez seja melhor colocar várias instâncias atrás de [[Elastic Load Balancing]] e usar [[Amazon EC2 Auto Scaling]].

---

## Exemplo prático

Em uma arquitetura simples, usuário, aplicação, rede, banco, armazenamento, segurança e monitoramento trabalham juntos. Instância [[Amazon EC2|EC2]] deve ser entendido pelo papel que exerce nesse conjunto.

---

## Diferenças importantes

Compare Instância [[Amazon EC2|EC2]] com conceitos próximos observando função, camada, responsabilidade e limite. Em nuvem, termos parecidos podem apontar para máquina, serviço gerenciado, tipo de capacidade ou política operacional.

---

## Cuidados

Uma instância [[Amazon EC2|EC2]] dá bastante controle, mas também traz responsabilidade.

Você precisa pensar em sistema operacional, patches, segurança, monitoramento, backup, escala e disponibilidade. Em serviços mais gerenciados, parte desse trabalho passa para a AWS.

Quando a necessidade é executar um servidor virtual com controle sobre sistema operacional, rede e armazenamento, a instância [[Amazon EC2|EC2]] é uma das abstrações centrais. Esse controle é útil, mas vem acompanhado de mais responsabilidade operacional.

---

## Relação com outras notas

- [[Amazon EC2]]
- [[Amazon Machine Image (AMI)]]
- [[Amazon VPC]]
- [[Security Groups]]
- [[Amazon EBS]]
- [[Elastic Load Balancing]]
- [[Amazon EC2 Auto Scaling]]

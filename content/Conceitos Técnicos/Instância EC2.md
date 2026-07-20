Uma instância EC2 é um servidor virtual criado pelo [[Amazon EC2]].

Ela é usada para executar aplicações, serviços, scripts, APIs, servidores web, workers, bancos autogerenciados ou qualquer workload que precise de uma máquina virtual.

---

## Visão geral

Quando você cria uma instância, a AWS provisiona capacidade computacional dentro da infraestrutura dela.

Você escolhe uma [[Amazon Machine Image (AMI)]], um tipo de instância, uma rede, uma subnet, regras de segurança, armazenamento e, em muitos casos, uma forma de acesso.

A instância passa a existir dentro de uma [[Amazon VPC]], com endereço IP privado e, se configurado, endereço público.

---

## O que acontece na prática

Imagine uma aplicação web simples.

Você pode criar uma instância EC2, instalar o servidor da aplicação, abrir as portas necessárias em [[Security Groups]] e anexar um volume [[Amazon EBS]] para armazenamento persistente.

Se a aplicação crescer, talvez seja melhor colocar várias instâncias atrás de [[Elastic Load Balancing]] e usar [[Amazon EC2 Auto Scaling]].

---

## Cuidado importante

Uma instância EC2 dá bastante controle, mas também traz responsabilidade.

Você precisa pensar em sistema operacional, patches, segurança, monitoramento, backup, escala e disponibilidade. Em serviços mais gerenciados, parte desse trabalho passa para a AWS.

Quando o cenário envolve em servidor virtual na AWS, instância EC2 costuma ser a associação mais direta.

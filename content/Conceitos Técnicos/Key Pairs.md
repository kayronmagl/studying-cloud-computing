Key pairs são pares de chaves usados para acessar instâncias [[Amazon EC2|EC2]] com segurança.

O par é formado por uma chave pública e uma chave privada. A AWS guarda a chave pública na instância, e você guarda a chave privada.

---

## O que é

Key Pairs deve ser entendido como vocabulário técnico que explica um comportamento real de sistemas. O termo ajuda a nomear algo que acontece em rede, computação, dados, segurança, desempenho ou operação.

---

## Por que existe

Key Pairs existe porque sistemas complexos precisam de nomes precisos. Quando o conceito é entendido, fica mais fácil diagnosticar problemas, comparar serviços e escolher arquitetura.

---

## Como funciona

Em instâncias Linux, key pairs são usados principalmente para acesso via SSH. Em instâncias Windows, ajudam no processo de obtenção da senha inicial de administrador.

A chave privada deve ser protegida. Se outra pessoa tiver acesso a ela, pode tentar acessar a instância, dependendo da rede e das permissões configuradas.

**O que acontece na prática**

Ao criar uma instância [[Amazon EC2|EC2]], você pode associar um key pair.

Depois, para acessar uma instância Linux pela rede, usa a chave privada no cliente SSH. O servidor valida se aquela chave privada corresponde à chave pública configurada.

Esse mecanismo evita depender apenas de senha.

---

## Exemplo prático

Em uma arquitetura simples, usuário, aplicação, rede, banco, armazenamento, segurança e monitoramento trabalham juntos. Key Pairs deve ser entendido pelo papel que exerce nesse conjunto.

---

## Diferenças importantes

Compare Key Pairs com termos vizinhos antes de usar a palavra como resposta. Conceitos parecidos podem atuar em camadas diferentes: aplicação, rede, armazenamento, banco, identidade ou operação.

---

## Cuidados

Key pair não é a mesma coisa que access key do [[AWS Identity and Access Management (IAM)|IAM]].

Key pair serve para acesso ao sistema operacional da instância. Access key do [[AWS Identity and Access Management (IAM)]] serve para chamadas de [[APIs|API]] da AWS.

Quando a dúvida envolve acesso SSH a uma instância [[Amazon EC2|EC2]], o key pair é parte do caminho de autenticação. Ele ainda depende de rede, usuário correto, permissões do arquivo de chave e regras de segurança permitindo a conexão.

---

## Relação com outras notas

- [[AWS Identity and Access Management (IAM)]]

Key pairs são pares de chaves usados para acessar instâncias EC2 com segurança.

O par é formado por uma chave pública e uma chave privada. A AWS guarda a chave pública na instância, e você guarda a chave privada.

---

## Visão geral

Em instâncias Linux, key pairs são usados principalmente para acesso via SSH. Em instâncias Windows, ajudam no processo de obtenção da senha inicial de administrador.

A chave privada deve ser protegida. Se outra pessoa tiver acesso a ela, pode tentar acessar a instância, dependendo da rede e das permissões configuradas.

---

## O que acontece na prática

Ao criar uma instância EC2, você pode associar um key pair.

Depois, para acessar uma instância Linux pela rede, usa a chave privada no cliente SSH. O servidor valida se aquela chave privada corresponde à chave pública configurada.

Esse mecanismo evita depender apenas de senha.

---

## Cuidado importante

Key pair não é a mesma coisa que access key do IAM.

Key pair serve para acesso ao sistema operacional da instância. Access key do [[AWS Identity and Access Management (IAM)]] serve para chamadas de API da AWS.

Quando o cenário envolve em acesso SSH a EC2, key pair costuma ser a associação mais direta.

Bare-metal é o uso direto de um servidor físico, sem a camada tradicional de virtualização que divide o mesmo hardware entre várias máquinas virtuais. O sistema operacional e as aplicações rodam sobre o equipamento real, com acesso mais direto a processador, memória, discos e interfaces de rede.

## Exemplo Prático

Esse modelo pode fazer sentido quando a carga de trabalho precisa de controle muito específico sobre o hardware, baixa variação de desempenho ou acesso direto a recursos físicos. Alguns bancos de dados, mecanismos de virtualização, aplicações de alto desempenho e softwares com licenciamento preso ao hardware podem exigir esse nível de controle.

O ganho vem acompanhado de responsabilidade. Quem usa bare-metal precisa lidar com instalação, atualização, falhas físicas, substituição de peças, capacidade ociosa e crescimento. Em nuvem, parte desse trabalho costuma ser abstraída por serviços de computação como [[Amazon EC2]], embora a abstração não elimine todas as decisões operacionais.

---

## Cuidados importantes

Bare-metal não significa automaticamente mais desempenho para qualquer sistema. Ele reduz uma camada de abstração, mas ainda depende de arquitetura, disco, rede, concorrência, sistema operacional e comportamento da aplicação. Em muitos casos, uma máquina virtual bem dimensionada ou um serviço gerenciado entrega resultado melhor com menos operação.

---

## Exemplo

Imagine uma aplicação que processa grandes volumes de dados com uso intenso de CPU e precisa manter latência previsível. Em bare-metal, a equipe pode escolher o servidor físico, controlar o sistema operacional e ajustar parâmetros de baixo nível. Em troca, também precisa planejar reposição de hardware, capacidade futura, manutenção e recuperação em caso de falha.

Esse contraste ajuda a entender por que a nuvem valoriza tanto abstrações de computação. Elas reduzem o contato direto com o hardware, mas continuam dependendo de servidores físicos nos data centers do provedor.

---

## Erros Comuns

Um erro comum é tratar bare-metal como o oposto absoluto de nuvem. A diferença principal não é apenas onde o servidor está, mas quanto controle físico e quanta responsabilidade operacional ficam com quem usa a infraestrutura.

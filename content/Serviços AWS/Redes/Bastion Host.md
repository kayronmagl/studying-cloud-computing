Bastion Host é uma instância posicionada como ponto controlado de acesso administrativo a recursos privados.

Em uma arquitetura tradicional, ele fica em uma [[Subnets Públicas|subnet pública]] e permite acesso a recursos em [[Subnets Privadas|subnets privadas]].

---

## Visão geral

Bastion Host faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Uso

O bastion recebe acesso SSH ou RDP de administradores autorizados.

A partir dele, o administrador acessa instâncias privadas.

---

## Por que Reduz Risco

Em vez de expor várias instâncias à internet, expõe-se um único ponto endurecido, monitorado e restrito.

---

## Alternativas Modernas

Serviços como AWS Systems Manager Session Manager podem reduzir ou eliminar necessidade de bastion em muitos cenários.

---

## Cuidado

Bastion host exposto é alvo sensível.

Deve ter MFA quando aplicável, IPs restritos, logs, patches, hardening e menor privilégio.

---

## Exemplo Prático

Uma aplicação web pode usar subnets públicas para load balancers, subnets privadas para instâncias e bancos, NAT Gateway para saída controlada e VPC Endpoints para acessar serviços AWS sem passar pela internet.

Cada componente muda segurança, custo e disponibilidade.

---

## Cuidados importantes

Rede mal desenhada pode gerar três problemas comuns:

* exposição indevida de recursos;
* falta de conectividade entre serviços;
* custo inesperado de tráfego.

Por isso, rede precisa ser estudada junto com segurança, alta disponibilidade e precificação.

AWS Direct Connect fornece conexão de rede dedicada entre uma infraestrutura externa e a AWS.

Ele é usado quando a empresa precisa de conectividade privada, previsível e controlada entre data center, colocation ou rede corporativa e a nuvem.


AWS Direct Connect faz parte do caminho que o tráfego percorre. Redes na AWS não são só “internet”: envolvem isolamento, rotas, subnets, DNS, gateways e regras de segurança.

Sempre pergunte: “quem precisa falar com quem, por qual caminho, e com qual permissão?”.

---

## Diferença para Internet Pública

Sem Direct Connect, tráfego entre empresa e AWS pode passar pela internet pública, mesmo usando criptografia.

Com Direct Connect, há um circuito dedicado até a AWS.

---

## Uso

* baixa variabilidade de latência;
* tráfego corporativo intenso;
* integração híbrida;
* requisitos de governança;
* conexão previsível;
* acesso a VPCs e serviços AWS.

---

## Relação com VPN

Direct Connect não é automaticamente criptografado como VPN.

Muitas arquiteturas combinam Direct Connect com criptografia adicional ou VPN, dependendo do requisito de segurança.

---

## Cuidado

Direct Connect exige planejamento físico, provedor, redundância e BGP.

Não é o primeiro passo para ambientes pequenos.

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

---

## Como entender isso

Este conceito pertence ao módulo de redes na AWS.

## Ponto central

Rede define isolamento, caminhos, exposição, conectividade privada, DNS e segurança de tráfego.

## Como Diferenciar

* VPC é regional.
* Subnet é zonal.
* Route table define caminho.
* Security group controla tráfego em recurso.
* NACL controla tráfego em subnet.
* NAT Gateway permite saída privada.

## Cuidado importante

Recurso em subnet pública só é realmente público se também tiver IP público e rota adequada.

---

## Pontos que Costumam Gerar Confusão

Quando o cenário envolve conexão privada dedicada entre data center on-premises e AWS, a resposta é [[AWS Direct Connect]].

---

## Como entender

Direct Connect cria uma conexão de rede dedicada, sem depender da internet pública como caminho principal.

---

## Comparação

* AWS Direct Connect: conexão privada dedicada.
* AWS VPN: túnel criptografado pela internet.
* [[Internet Gateway]]: conecta VPC à internet.
* CloudFront: CDN de borda.

---

## Acesso remoto e conectividade

Além de conexões dedicadas como Direct Connect, [[AWS Client VPN]] aparece quando usuários precisam acessar recursos privados da AWS de forma remota e segura.

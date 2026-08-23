AWS Trusted Advisor é um serviço que analisa o ambiente AWS e mostra recomendações de boas práticas.

Ele ajuda a encontrar pontos de melhoria em custo, segurança, desempenho, tolerância a falhas e limites de serviço. A ideia é simples: em vez de você procurar manualmente cada risco ou desperdício, o Trusted Advisor aponta verificações que merecem atenção.

Pense no Trusted Advisor como uma revisão automática do ambiente.

Ele não substitui arquitetura, monitoramento ou segurança bem configurada. Ele funciona como um apoio para encontrar problemas comuns, como permissões perigosas, ausência de MFA no usuário root, uso ineficiente de recursos ou limites próximos de serem atingidos.

---

## O que é

AWS Trusted Advisor deve ser entendido como parte do controle econômico da nuvem. Custo em nuvem vem de uso medido: tempo ligado, armazenamento, requisições, tráfego, logs, suporte, planos e compromissos.

---

## Por que existe

AWS Trusted Advisor existe para tornar consumo, custo, suporte e decisão financeira mais visíveis. Em nuvem, gasto muda conforme uso, região, tráfego, armazenamento, logs, planos e escolhas operacionais.

---

## Como funciona

O Trusted Advisor executa verificações e mostra recomendações. Algumas verificações ficam disponíveis mesmo em planos básicos, mas o conjunto completo depende do plano de suporte.

Nos planos atuais da AWS, clientes com [[AWS Business Support+]], [[AWS Enterprise Support]] ou [[AWS Unified Operations]] conseguem acessar o conjunto completo de verificações do Trusted Advisor.

Clientes em planos Basic ou Developer têm acesso limitado, incluindo verificações de limites de serviço e algumas verificações de segurança e tolerância a falhas.

---

## Exemplo prático

Uma equipe pode descobrir custo inesperado por NAT Gateway, snapshots antigos, logs excessivos ou transferência de dados entre regiões. Nesse cenário, AWS Trusted Advisor ajuda a entender, acompanhar ou controlar impacto financeiro e operacional.

---

## Diferenças importantes

**Diferença para serviços parecidos**

| Serviço | Ideia principal |
|---|---|
| AWS Trusted Advisor | Recomenda boas práticas no ambiente AWS |
| Amazon CloudWatch | Observa métricas, logs e alarmes |
| AWS CloudTrail | Registra chamadas de [[APIs|API]] e ações de usuários |
| AWS Config | Avalia configurações e mudanças em recursos |
| Amazon GuardDuty | Detecta ameaças e comportamento suspeito |

**Como Diferenciar**

Quando o cenário que envolve todas as verificações do Trusted Advisor, associe a planos de suporte pagos de nível mais alto, como Business/Business Support+, Enterprise ou Unified Operations, dependendo da nomenclatura usada no material.

---

## Cuidados

O erro comum é olhar apenas o preço unitário. O custo real depende de uso contínuo, tráfego, armazenamento acumulado, logs, região, suporte, ociosidade e governança.

---

## Relação com outras notas

- [[AWS Business Support+]]
- [[AWS Enterprise Support]]
- [[AWS Unified Operations]]

Landing Zone é um ambiente base preparado para receber workloads na nuvem de forma segura, governada e escalável.

Ela normalmente inclui contas, redes, identidade, logs, segurança, padrões e automação.

---

## Visão geral

Antes de colocar aplicações importantes na AWS, a empresa precisa preparar o terreno.

Esse terreno é a landing zone.

Ela evita que cada equipe crie recursos sem padrão, sem logs, sem segurança e sem organização de contas.

---

## O que uma Landing Zone costuma ter

* estrutura de contas;
* [[AWS Organizations]];
* políticas;
* redes base;
* logs centralizados;
* trilhas de auditoria;
* controles de segurança;
* integração com identidade;
* padrões de tags;
* automação de provisionamento;
* monitoramento inicial.

---

## Relação com AWS CAF

Landing zone se conecta principalmente com a [[Perspectiva de Plataforma do AWS CAF]], mas também depende de governança, segurança e operações.

---

## Como Diferenciar

Quando o cenário envolve em preparar ambiente base para adoção de nuvem em escala, landing zone costuma ser a associação mais direta.

---

## Cuidado importante

Landing zone não é uma aplicação.

É a fundação onde aplicações serão implantadas com controle e consistência.

---

## Como Analisar o Cenário

Quando o cenário envolve ambiente base, fundação, contas, redes, logs, segurança e governança, pense em landing zone.

Ela aparece antes da migração em escala.

---

## Exemplo explicado

Antes de migrar aplicações, a empresa cria uma estrutura multi-conta com logging centralizado, redes, políticas, identidade, auditoria e padrões de segurança.

Isso é landing zone.

---

## Relação com Control Tower

[[AWS Control Tower]] ajuda a configurar e governar ambientes multi-conta, frequentemente associado à criação de landing zones.

---

## Ideia Central

* Landing Zone: terreno preparado para workloads na nuvem..


---

## Outra forma de entender

Uma boa resposta precisa ter três partes:


* definição: o que é.
* função: para que serve na adoção da nuvem.
* diferença: com o que não deve ser confundido.


No contexto do AWS CAF, o objetivo não é decorar nomes. O objetivo é reconhecer qual área da organização precisa amadurecer.

Quando o cenário descreve um problema, identifique se ele é de negócio, pessoas, governança, plataforma, segurança ou operações. Essa leitura normalmente entrega a resposta.

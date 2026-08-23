Eficiência de Desempenho é um pilar do AWS Well-Architected Framework.

Ele foca em usar recursos de computação de maneira eficiente para atender aos requisitos do sistema e manter essa eficiência conforme a demanda muda.

Uma pergunta desse pilar é:

* estou usando o tipo certo de recurso para o trabalho certo?

Não basta escolher o maior servidor.

É preciso escolher recursos adequados, testar desempenho, monitorar métricas e ajustar conforme a aplicação evolui.

---

## O que é

Eficiência de desempenho é escolher o recurso certo para o trabalho certo.

Não é usar sempre o maior servidor. É entender a necessidade do sistema e escolher a melhor combinação.

---

## Por que existe

Eficiência de Desempenho existe para orientar decisões que não são apenas técnicas. Adoção de nuvem envolve pessoas, processos, risco, plataforma, segurança, operação, custo e valor de negócio.

---

## Como funciona

**Como reconhecer em perguntas na prática**

Uma forma comum desse assunto aparecer é:

* usar recursos de computação de maneiras que atendam aos requisitos do sistema

A resposta é Eficiência de desempenho.

---

## Exemplo prático

* escolher família correta de [[Amazon EC2|EC2]];
* usar cache quando necessário;
* escolher banco adequado ao padrão de acesso;
* escalar horizontalmente;
* usar serverless quando apropriado;
* monitorar latência, throughput e erro;
* testar com carga realista.

Se a aplicação precisa responder usuários no mundo todo, talvez [[Amazon CloudFront]] ajude mais do que aumentar instância [[Amazon EC2|EC2]].

Se o problema é leitura repetida, talvez cache ajude.

Se o acesso é por chave em grande escala, talvez [[Amazon DynamoDB]] seja melhor que um banco relacional.

---

## Diferenças importantes

**Como Diferenciar**

A frase de prova é parecida com:

* usar recursos de computação de maneiras que atendam aos requisitos do sistema

A resposta é Eficiência de Desempenho.

**Comparação com outros pilares**

* Confiabilidade: recuperar de falhas.
* Segurança: proteger dados e sistemas.
* Excelência operacional: operar e melhorar continuamente.
* Eficiência de desempenho: usar recursos adequados para performance.

---

## Cuidados

Eficiência de desempenho não é simplesmente “custo baixo”.

O foco é atender requisitos de performance com recursos apropriados.

Não confunda com confiabilidade.

* Confiabilidade: recuperar de falhas.
* Eficiência de desempenho: atender requisitos de performance com recursos adequados.

---

## Relação com outras notas

- [[Amazon CloudFront]]
- [[Amazon DynamoDB]]

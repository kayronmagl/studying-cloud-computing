Eficiência de Desempenho é um pilar do AWS Well-Architected Framework.

Ele foca em usar recursos de computação de maneira eficiente para atender aos requisitos do sistema e manter essa eficiência conforme a demanda muda.

---

## Visão geral

Uma pergunta desse pilar é:


* estou usando o tipo certo de recurso para o trabalho certo?


Não basta escolher o maior servidor.

É preciso escolher recursos adequados, testar desempenho, monitorar métricas e ajustar conforme a aplicação evolui.

---

## Como Diferenciar

A frase de prova é parecida com:


* usar recursos de computação de maneiras que atendam aos requisitos do sistema


A resposta é Eficiência de Desempenho.

---

## Exemplos

* escolher família correta de EC2;
* usar cache quando necessário;
* escolher banco adequado ao padrão de acesso;
* escalar horizontalmente;
* usar serverless quando apropriado;
* monitorar latência, throughput e erro;
* testar com carga realista.

---

## Comparação com outros pilares

* Confiabilidade: recuperar de falhas.
* Segurança: proteger dados e sistemas.
* Excelência operacional: operar e melhorar continuamente.
* Eficiência de desempenho: usar recursos adequados para performance.


---

## Cuidado importante

Eficiência de desempenho não é simplesmente “custo baixo”.

O foco é atender requisitos de performance com recursos apropriados.

---

## Explicação principal

Eficiência de desempenho é escolher o recurso certo para o trabalho certo.

Não é usar sempre o maior servidor. É entender a necessidade do sistema e escolher a melhor combinação.

---

## Exemplo

Se a aplicação precisa responder usuários no mundo todo, talvez [[Amazon CloudFront]] ajude mais do que aumentar instância EC2.

Se o problema é leitura repetida, talvez cache ajude.

Se o acesso é por chave em grande escala, talvez [[Amazon DynamoDB]] seja melhor que um banco relacional.

---

## Como reconhecer em perguntas na prática

Uma forma comum desse assunto aparecer é:


* usar recursos de computação de maneiras que atendam aos requisitos do sistema


A resposta é Eficiência de desempenho.

---

## Cuidado importante na prática

Não confunda com confiabilidade.


* Confiabilidade: recuperar de falhas.
* Eficiência de desempenho: atender requisitos de performance com recursos adequados.

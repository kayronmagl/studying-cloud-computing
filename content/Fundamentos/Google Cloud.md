Google Cloud é o provedor de nuvem do Google. Ele oferece serviços de computação, armazenamento, bancos de dados, redes, segurança, análise de dados e inteligência artificial, usando a infraestrutura operada pelo próprio Google.

## Exemplo Prático

Uma aplicação hospedada no Google Cloud pode executar código em máquinas virtuais, armazenar arquivos em um serviço de objetos, usar bancos gerenciados e publicar conteúdo por uma rede global. A lógica geral é a mesma de outros provedores: recursos de TI são provisionados sob demanda e cobrados conforme o uso, mas os nomes dos serviços, integrações e decisões de implementação são próprios do Google.

Por isso, ao estudar Google Cloud ao lado de [[AWS (Amazon Web Services)]] e [[Microsoft Azure]], o mais importante é separar o conceito geral do produto específico. Computação, rede, identidade e banco de dados existem em todos os provedores, mas cada plataforma organiza esses recursos de um jeito.

---

## Cuidados importantes

Não é correto aprender computação em nuvem como se cada provedor fosse um universo sem relação com os outros. Também não é correto imaginar que serviços com nomes parecidos tenham sempre o mesmo comportamento. A comparação precisa começar pelo mecanismo: tipo de computação, modelo de armazenamento, padrão de rede, forma de cobrança, responsabilidade operacional e integração com outros serviços.

---

## Exemplo

Se uma equipe migra uma aplicação para Google Cloud, ela pode escolher máquinas virtuais para manter controle sobre o sistema operacional ou serviços mais gerenciados para reduzir operação. A decisão não deve partir apenas do nome do serviço, mas do que a aplicação precisa: tempo de resposta, volume de dados, segurança, previsibilidade de custo e esforço de manutenção.

Essa leitura também ajuda a evitar propaganda técnica. Google Cloud é uma implementação de nuvem pública, não a definição de computação em nuvem.

---

## Erros Comuns

Um erro comum é comparar provedores apenas por listas de serviços. A pergunta mais útil costuma ser: qual problema técnico a aplicação tem, qual modelo de operação a equipe aceita e qual serviço resolve esse problema com menos risco para aquele contexto?

S3 Intelligent-Tiering é uma classe de armazenamento do Amazon S3 para objetos cujo padrão de acesso é desconhecido ou muda com o tempo.

Ela monitora o acesso aos objetos e os move automaticamente entre camadas de custo, sem exigir que você adivinhe manualmente se o dado será muito ou pouco acessado.


O S3 Intelligent-Tiering faz sentido quando você não sabe como o dado será acessado.

Um arquivo pode ser muito usado nos primeiros dias e quase nunca depois. Outro pode ficar meses parado e voltar a ser acessado de repente. Nesses casos, escolher uma classe fixa pode ser ruim.

O Intelligent-Tiering começa colocando objetos em uma camada de acesso frequente. Depois, se o objeto não for acessado por determinado período, ele pode ser movido para camadas de acesso menos frequente e menor custo.

---

## Diferença para outras classes

| Classe | Quando faz sentido |
|---|---|
| S3 Standard | Acesso frequente e baixa latência |
| S3 Standard-IA | Acesso infrequente já esperado |
| S3 One Zone-IA | Acesso infrequente em apenas uma zona |
| S3 Glacier Flexible Retrieval | Arquivamento com recuperação mais lenta |
| S3 Intelligent-Tiering | Acesso desconhecido, variável ou imprevisível |

---

## Como Diferenciar



---

## Exemplo aplicado

Uma empresa guarda relatórios, imagens e documentos que mudam de frequência de acesso ao longo do tempo.

Alguns arquivos são muito acessados no começo e depois quase nunca mais. Outros ficam parados por meses e voltam a ser consultados. O Intelligent-Tiering reduz a necessidade de escolher manualmente uma classe fixa antes de saber o comportamento real do dado.

---

## Cuidado de custo

O Intelligent-Tiering reduz a necessidade de prever manualmente o padrão de acesso, mas isso não significa que ele seja sempre a melhor escolha.

Ele cobra uma pequena taxa de monitoramento e automação por objeto. Por isso, faz mais sentido quando os objetos têm tamanho e padrão de acesso que justificam essa automação.

A lógica é: quando o acesso é imprevisível, Intelligent-Tiering pode ajudar. Quando o padrão já é conhecido, uma classe fixa pode ser suficiente.

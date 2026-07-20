AWS Snowball foi o nome original de uma linha de dispositivos físicos usados para transferir grandes volumes de dados entre ambientes locais e a AWS.

Com a evolução do produto, o nome passou a aparecer principalmente associado ao [[AWS Snowball Edge]], que adicionou capacidade computacional e modelos de armazenamento mais avançados.

---

## Problema que Resolvia

Quando a conexão disponível não conseguia transferir terabytes ou petabytes em uma janela aceitável, o cliente copiava os dados para um dispositivo local e o devolvia à AWS. O conteúdo era então importado, geralmente para [[Amazon S3]].

Esse processo reduzia a dependência da internet, mas exigia logística, planejamento de cópia, criptografia e validação após a importação.

---

## Situação Atual

As gerações antigas de Snowball foram descontinuadas. O [[AWS Snowball Edge]] deixou de aceitar novos clientes em 7 de novembro de 2025.

O termo Snowball ainda é útil para compreender arquiteturas existentes e a história da transferência offline na AWS, mas não deve ser tratado como escolha normal para um projeto novo.

---

## Alternativas

Para novos projetos, considere [[AWS DataSync]], [[AWS Direct Connect]], AWS Data Transfer Terminal ou soluções de parceiros, conforme volume, prazo, conectividade e necessidade de transporte físico.

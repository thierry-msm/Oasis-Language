# 🎸 Projeto de Compiladores: Linguagem Oasis (T01)

Este projeto consiste no desenvolvimento de um analisador léxico e sintático utilizando a ferramenta **JavaCC**. O objetivo acadêmico é construir a base de um compilador capaz de validar códigos-fonte escritos em uma linguagem de programação personalizada.

> **Nota sobre o nome do arquivo:** Embora a linguagem projetada se chame **Oasis** (com uma temática fortemente baseada em música), o arquivo principal do parser foi nomeado como `T01.jj`. Esta adequação foi feita estritamente para atender aos requisitos de correção automática da disciplina.

---

## 🎶 A Linguagem "Oasis"

A linguagem Oasis foi desenhada para trazer a emoção de compor um álbum de rock para o mundo da programação. As estruturas de controle clássicas (if, while, funções, tipos) foram substituídas por jargões musicais, tornando o código divertido e semântico para quem é fã de música.

### Palavras-chave e Seus Significados

| Termo em Oasis | Estrutura Clássica Equivalente | Descrição |
| :--- | :--- | :--- |
| `track` | `function` / `void` | Declaração de uma nova função (uma "faixa" do álbum). |
| `verse` | `if` | Estrutura condicional principal. |
| `bridge` | `else` / `else if` | Caminho alternativo da condicional. |
| `chorus` | `while` | Estrutura de repetição (o refrão que se repete). |
| `play` | `call` | Chamada de execução de uma função existente. |
| `encore` | `return` | Retorna um valor no fim de uma execução. |
| `mic_drop` | `print` / `echo` | Imprime um valor ou variável na tela (no console). |

### Tipos de Dados Suportados

Os tipos primitivos também ganharam nomes de gêneros musicais:
* **`pop`**: Representa números inteiros (`int`).
* **`rock`**: Representa cadeias de caracteres (`String`).
* **`jazz`**: Representa valores lógicos/booleanos (`boolean`: `true` ou `false`).
* **`classical`**: Usado para funções que não têm retorno (`void`).

---

## ⚙️ Estrutura do Código Oasis

A gramática permite a criação de um código estruturado de cima para baixo. Um programa ("Álbum") é formado por uma lista de declarações globais de variáveis ou declarações de funções.

**Exemplo prático (O famoso Hello World):**
~~~text
track soundcheck() : classical {
    rock saudacao;
    saudacao = "Hello Music!";
    mic_drop saudacao;
}
~~~

---

## 🧪 Suíte de Testes (Quality Assurance)

Para validar a robustez da gramática descrita no `T01.jj`, foram criados **25 arquivos de teste** que cobrem todos os cenários possíveis de uso da linguagem, além de forçar a captura correta de erros.

Os testes estão divididos em três categorias:

### 1. Testes Válidos (`teste01.txt` a `teste10.txt`)
Scripts que seguem rigorosamente a gramática e devem ser aprovados com a mensagem *"Álbum validado com sucesso!"*.
* **01 a 03:** Declarações, estruturas de repetição aninhadas (`chorus`) e condicionais complexas (`verse`/`bridge`).
* **04 a 06:** Chamadas de funções com múltiplos parâmetros, precedência matemática e escopo global.
* **07 a 10:** Expressões lógicas diretas, variação de tipos de dados, composição de funções e um código final unindo tudo ("Sinfonia").

### 2. Testes Inválidos / Erros Esperados (`teste11.txt` a `teste20.txt`)
Scripts contendo erros clássicos de programação que devem ser barrados pelo parser com a mensagem *"Nota fora do tom!"*, capturando a `ParseException`.
* **Exemplos de falhas:** Falta de ponto e vírgula, `bridge` sem `verse` (else sem if), tipos inexistentes, fechamento incorreto de chaves e operadores matemáticos mal posicionados.

### 3. Testes de Mutação (`teste21.txt` a `teste25.txt`)
Cenários com erros muito sutis e específicos, criados a partir de mutações diretas dos testes válidos, para garantir que as restrições impostas no `.jj` estão firmes.
* **Exemplos:** Uso de `verse` sem os parênteses obrigatórios, declaração e atribuição na mesma linha (não suportado), esquecimento do token de dois pontos `:` na assinatura da função e statements vazios irregulares.

---

## 🚀 Como Executar o Projeto (Eclipse)

1. Certifique-se de ter o plugin do **JavaCC** instalado na sua IDE.
2. Compile o arquivo **`T01.jj`** (Isso gerará as classes Java do parser, incluindo a principal `T01.java`).
3. Ajuste o caminho da leitura de arquivo no método `main` da classe `T01.java` para apontar para o arquivo de teste desejado (ex: `src/RiffCode/teste01.txt`).
4. Clique com o botão direito em `T01.java` -> **Run As** -> **Java Application**.
5. O resultado da análise sintática aparecerá no **Console**.

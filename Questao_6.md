### [QUESTÃO – 7]
### Descreva a redução (prove a NP-Completude) do problema do SAT ao Clique. Apresente o pseudo-código do algoritmo NP e mostre graficamente as instâncias e soluções, no processo de redução.

#### A) Problema SAT x Teoria da NP-Completude.
* Problema SAT: O problema de satisfatibilidade booleana (SAT) foi reconhecidamente um dos primeiros problemas NP-complet. Consiste em determinar se uma dada fórmula booleana é satisfeita ou não. As expressões booleanas podem ser constituída de:

  - Variáveis, que podem assumir o valor 0 (Falso) e 1 (Verdadeiro).  
  - Operadores binários lógicos AND e OR.  
  - Operadores unitários geralmente repesentado pelo caracter ¬ representando uma negação.
  - Parênteses para agrupar os operadores e variáveis para estabelecer uma precedência.  
  
  O problema pode se tornar mais simples caso seja restringido a uma forma normal disjuntiva, onde as fórmulas lógicas são represntadas por conjunções (OR) de cláusulas disjuntivas (AND).

* Teoria da NP-Completude: O problema central na teoria da NP-completude é o problema de satisfatibilidade booleana (SAT). A teoria consiste na seguinte definição:   

  Dado um problema de decisão P, podemos reduzí-lo a um problema P' se existe uma função (MT) f : P → P', ou seja, existe uma função que transforma qualquer instância p ∈ P em um a instância p' ∈ P' e que uma solução para p pode ser obtida da solução de p'.

  Em outras palavras, não basta que um problema seja reduzido em outro problema. É necessário que essa redução seja polinomial.
  
#### B) Classes P, NP, NP-Difícil e NP-Completo.
  * Os problemas determinados em P, referen-se aos problemas que podem ser resolvidos em tempo polinomial por uma máquina de Turing determinística. Qualquer problema deste conjunto pode ser resolvido por um algoritmo com tempo de execução O(n^{k}), (com k constante).

    Denota-se por NP os problemas que são resolvidos em tempo polinomial por uma máquina de Turing não-determinístico. Nos anos 1970 Stephen Cook e Leonid Levin descobriram um grupo especial de problemas contidos em NP onde a complexidade relaciona-se com a complexidade de toda a classe. Isso permite que, caso haja uma solução para um destes problemas, todos os problemas em NP serão resolvidos em tempo polinomial. Este grupo é chamado de NP-completos.

    Já um problema X é dito NP-difícil se todos os problemas em NP não são mais difíceis que X.

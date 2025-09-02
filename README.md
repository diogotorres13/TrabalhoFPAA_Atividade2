# MaxMin Select -- Algoritmo de Seleção Simultânea

Este projeto apresenta a implementação, em Python, do algoritmo **MaxMin
Select**, que encontra simultaneamente o menor e o maior valor de uma
lista de números, aplicando a técnica de **divisão e conquista**.

## Visão Geral

O **MaxMin Select** é um algoritmo recursivo que permite determinar o
valor mínimo e o valor máximo de forma mais eficiente do que a busca
sequencial ingênua.\
A estratégia adotada consiste em dividir o problema em subconjuntos,
resolver cada um deles recursivamente e, por fim, reunir os resultados
para obter a resposta final.

### Funcionamento do Algoritmo

1.  **Um único elemento** → Se o intervalo possuir apenas um item, este
    representa tanto o menor quanto o maior valor.\
2.  **Dois elementos** → Caso o intervalo contenha dois itens, basta uma
    comparação para decidir qual deles é o maior e qual é o menor.\
3.  **Mais de dois elementos** → Para listas maiores:
    -   Divide-se o intervalo em duas metades.\
    -   Executa-se recursivamente o procedimento em cada metade.\
    -   Combina-se o resultado comparando os menores e maiores
        encontrados em cada parte.

### Exemplo Prático

Dada a lista `[5, 2, 8, 1, 9, 3, 7, 4, 6]`:

-   Primeiro, divide-se em `[5, 2, 8, 1]` e `[9, 3, 7, 4, 6]`.\
-   Cada subconjunto é processado de forma recursiva.\
-   Na fase de combinação, encontramos que o menor valor é **1** e o
    maior valor é **9**.

## Como Executar

1.  Clone o repositório no seu computador:

``` bash
git clone https://github.com/diogotorres13/TrabalhoFPAA_Atividade2.git
```

2.  Acesse a pasta do projeto:

``` bash
cd TrabalhoFPAA_Atividade2
```

3.  Rode o programa:

``` bash
python main.py
```

## Relatório Técnico

### Análise por Contagem de Operações

Considerando uma lista de tamanho **n**:

-   **Divisão** → em cada etapa, o vetor é dividido ao meio, o que
    demanda apenas um cálculo de índice (O(1)).\
-   **Recursão** → duas chamadas recursivas são realizadas, cada uma
    tratando n/2 elementos.\
-   **Combinação** → ao unir os resultados, são feitas duas comparações
    (menor entre os mínimos e maior entre os máximos).

Somando todas as etapas, o total de comparações é **2n - 2**, o que
implica em complexidade **O(n)**.

### Análise pelo Teorema Mestre

A recorrência do algoritmo é:

\[ T(n) = 2T`\left`{=tex}(`\frac{n}{2}`{=tex}`\right`{=tex}) + O(1) \]

1.  **Parâmetros identificados**:
    -   a = 2 (número de subproblemas)\
    -   b = 2 (fator de divisão)\
    -   f(n) = O(1) (custo da combinação)
2.  **Cálculo de log_b(a)**:
    -   log₂(2) = 1
3.  **Aplicação do Teorema Mestre**:
    -   Como f(n) = O(1) = O(n\^log₂(2)) = O(n¹), trata-se do **Caso
        1**.
4.  **Resultado**:
    -   ( T(n) = O(n) )



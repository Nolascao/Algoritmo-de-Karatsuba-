# Algoritmo de Karatsuba 
O algoritmo de Karatsuba é um método eficiente para a multiplicação de dois números inteiros grandes. Ele foi desenvolvido pelo matemático russo Anatolii Alexeevitch Karatsuba em 1960 e é considerado um dos primeiros algoritmos rápidos de multiplicação que superam o método tradicional (também conhecido como "multiplicação longa" ou "método da escola").

## Como funciona o algoritmo de Karatsuba?
O algoritmo de Karatsuba utiliza uma abordagem baseada no conceito de divisão e conquista (divide and conquer). Em vez de realizar a multiplicação diretamente, ele divide os números em partes menores, realiza cálculos intermediários e combina os resultados para obter o produto final. Isso reduz o número total de operações necessárias, tornando-o mais eficiente do que o método tradicional.

## Ideia principal
Dado dois números ( x ) e ( y ), o algoritmo de Karatsuba reduz a multiplicação desses números ao cálculo de três multiplicações menores e algumas somas e subtrações. Para isso:

Os números ( x ) e ( y ) são divididos em duas partes:
( x = x_1 \cdot 10^m + x_0 )
( y = y_1 \cdot 10^m + y_0 )
Onde:
( x_1 ) e ( y_1 ) representam as partes mais significativas (dígitos mais à esquerda).
( x_0 ) e ( y_0 ) representam as partes menos significativas (ditos mais à direita).
( m ) é o ponto onde os números são divididos, geralmente a metade do número de dígitos.
O produto ( x \cdot y ) pode ser calculado usando a fórmula: [ x \cdot y = z_2 \cdot 10^{2m} + z_1 \cdot 10^m + z_0 ] Onde:
( z_0 = x_0 \cdot y_0 ) (produto das partes menos significativas),
( z_2 = x_1 \cdot y_1 ) (produto das partes mais significativas),
( z_1 = (x_1 + x_0) \cdot (y_1 + y_0) - z_2 - z_0 ) (produto cruzado ajustado).
A fórmula evita a necessidade de calcular quatro multiplicações separadas (como no método tradicional), reduzindo-as para apenas três multiplicações recursivas (( z_0 ), ( z_1 ), ( z_2 )) e algumas operações adicionais de soma e subtração. 

## Lógica de Como foi Implementado 

Linha 3-4: Caso base, em que, se os parâmetros forem menores que 10, executa a multiplicação normalmente por ser mais eficaz
Linha 5-8: Determina o tamanho dos números 
Linha 9-12: Divide os números em duas partes
Linha 13-17: Calcula os três produtos necessários para aplicar a fórmula de karatsuba
Linha 18-20: Retorna o resultado da fórmula de karatsuba

## Complexidade
No método tradicional, a multiplicação de dois números com ( n ) dígitos tem complexidade ( O(n^2) ), pois cada dígito de um número é multiplicado por cada dígito do outro.
O algoritmo de Karatsuba reduz essa complexidade para aproximadamente ( O(n^{\log_2{3}}) ), ou seja, cerca de ( O(n^{1.585}) ). Isso o torna significativamente mais rápido para números muito grandes.
Vantagens
Mais eficiente para números grandes: O algoritmo é ideal para cenários onde os números possuem muitos dígitos, como na criptografia ou computação científica.
Base para outros algoritmos: O Karatsuba é frequentemente usado como base para algoritmos ainda mais avançados de multiplicação rápida, como o algoritmo de Toom-Cook e a multiplicação por transformada rápida de Fourier (FFT).
## Desvantagens
Overhead para números pequenos: Para números pequenos, o método tradicional pode ser mais rápido devido ao overhead causado pelas operações adicionais (somas e subtrações) e pela recursão.
Implementação mais complexa: Comparado ao método tradicional, o Karatsuba é mais difícil de implementar corretamente.

## Dependências
Nenhuma 

## Como Roda o Projeto
Passo 1: 
Entre no arquivo "Code/.venv/Lib/site-packages/pip/__main__.py" utilizando sua IDE de preferência

Passo 2: 
Rode o arquivo.

## Versão do Python
Este projeto foi desenvolvido na versão 3.13.0 do Python.

##Explicação das funções
### Arquivo: 
__main__.py
### Objetivo: 
Este arquivo principal realiza a multiplicação de dois número inteiros utilizando o algoritmo de karatsuba.
### Descrição das funções:
karatsuba(x,y)
Recebe dois números e, caso eles tiverem 4 ou mais algarismos, utiliza o método de karatsuba para multiplicá-los.
Parâmetros:
x: Primeiro número
y: Segundo número
Retorno:
Resultado da multiplicação dos dois números

# Relatório Técnico 

## Fluxo de Controle da Função 

1. Início da Função
2. Verificação da condição x < 10 or y < 10
   - Se verdadeiro: retorna x* y
   - Se falso: Passa direto para a próxima iteração
3. Inicializa a variável n
4. Inicializa a variável m
5. Inicializa as variáveis high_x e low_x
6. Inicializa as variáveis high_y e low_y
7. Inicializa a variável z0
8. Inicializa a variável z1
9. Inicializa a variável z2
10. Retorna o resultado da fórmula de karatsuba

Nós: 
1. Início da Função
2. Verificação do if
3. Ação dentro do if
4. Inicializaçao de n
5. Inicializaçao de m
6. Inicialização das variáveis high_x e low_x
6. Inicialização das variáveis high_y e low_y
7. Inicialização da variável z0
8. Inicialização da variável z1
9. Inicialização da variável z2
10. Retorno final

Arestas: 
1. Inicio do nó para verificação do if
2. Verificação do If para ação dentro do if
3. Verificação do If para retorno final
4. Ação dentro do if para inicialização de n
5. Inicialização de n para inicialização de m
6. Inicialização de m para inicialização das variáveis high_x e low_x
7. Inicalização das variáveis high_x e low_x para a Inicialização das variáveis high_y e low_y
8. Inicialização das variáveis high_y e low_y para inicialização da variável z0
9. Inicialização da variável z0 para inicialização da variável z1
10. Inicialização da variável z1 para inicialização da variável z2
11. Inicialização da variável z2 para retorno final

![image](https://github.com/user-attachments/assets/484c115e-989b-440d-921a-9b230a38165a)

### Complexidade Ciclomática = E - N + 2P = 11 - 10 + 2*1 = 3 

### Complexidade Assintótica

**Complexidade temporal:** 
- Melhor caso: O(1)
- Caso Médio: O(n^{1.585})
- Pior caso: O(n^{1.585})

**Complexidade Espacial:**
- Melhor caso: O(1)
- Caso Médio: (O(\log n)
- Pior Caso: O(\log n)

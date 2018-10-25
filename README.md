
# Método de Gauss-Seidel 

##  Definição

O **método de Gauss-Seidel** é um método iterativo para resolução de sistemas de equações lineares. É semelhante ao método de Jacobi (e como tal, obedece ao mesmo critério de convergência). É condição suficiente de convergência que a matriz seja estritamente diagonal dominante, fica garantida a convergência da sucessão de valores gerados para a solução exata do sistema linear.

## Descrição do método
 
 - O método de Gauss-Seidel é um método iterativo e, portanto, é bastante eficiente. Começa propondo o sistema de equações com o qual ele vai funcionar:

   ![](http://www.monografias.com/trabajos45/descomposicion-lu/Image41.gif)

Da equação 1 para limpar $x_{1}$, da equação 2 para limpar  $x_{2}$, ..., da equação n para limpar x$_n$. Isto dá o seguinte conjunto de equações:

   ![enter image description here](http://www.monografias.com/trabajos45/descomposicion-lu/Image42.gif)
   
Esste último conjunto de equações são as que formam as fórmulas iterativas com as quais você estará trabalhando. Para iniciar o **processo iterativo**, o valor zero é dado às variáveis $x_{2}$, ..., x$_n$; isso dará um primeiro valor para  $x_{1}$. Mais precisamente, tem que:

![enter image description here](http://www.monografias.com/trabajos45/descomposicion-lu/Image43.gif)

Em seguida, substituímos este valor de $x_{1}$ na equação 2, e as variáveis ​​$x_{3}$, ..., x$_n$ ainda têm o valor zero. Isto dá o seguinte valor para $x_{2}$:

![enter image description here](http://www.monografias.com/trabajos45/descomposicion-lu/Image44.gif)

Estes últimos valores de $x_{1}$ e $x_{2}$ são substituídos na equação 3, enquanto$x_{4}$, ..., x$_n$ ainda tem o valor zero; e assim por diante até chegar à última equação. Todo este passo produzirá uma lista dos primeiros valores para os desconhecidos, que formam o primeiro passo no processo iterativo. Para uma melhor compreensão, isso será simbolizado desta maneira:

![enter image description here](http://www.monografias.com/trabajos45/descomposicion-lu/Image45.gif)

O processo é repetido, mas agora substituindo os últimos dados em vez de zeros como no começo. Uma segunda lista de valores será obtida para cada um dos desconhecidos, que serão simbolizados da seguinte forma:

![enter image description here](http://www.monografias.com/trabajos45/descomposicion-lu/Image46.gif)

Neste momento você pode calcular os erros relativos aproximados, com relação a cada um dos desconhecidos. A lista de erros é apresentada abaixo:

![enter image description here](http://www.monografias.com/trabajos45/descomposicion-lu/Image47.gif)

O processo é repetido até:

![enter image description here](http://www.monografias.com/trabajos45/descomposicion-lu/Image48.gif)


##  Vantagens

O método de Gauss-Seidel é uma variante do Gauss Jacobi, onde se busca acelerar a solução. Em princípio esse método tende a convergir mais rápido que o de Jacobi.

##  Desvantagens

 Havendo casos em que isso não ocorre por compensação de erros.
 
## Exemplo

**1**. Resolva o sistema linear a seguir pelo método Gauss-Seidel com $X^{(0)}$ =  $[0 0 0 ]^{T}$  e  $\epsilon$ = $5*10^{-2}.$

$5x_{1}$ + $x_{2}$ + $x_{3}$ = 5
$3x_{1}$ + $x_{2}$ + $x_{3}$ =6
$3x_{1}$ + $x_{2}$ + $x_{3}$ = 0

**Solução:**

O processo iterativo é obtido da mesma forma que o método de Jacobi, exceto pela avaliação consecutiva das iteradas a partir das componentes previamente conhecidas. Assim, temos:

$x_1^{k+1}$ = 1 - 0.2$x_2^{(k)}$ + $x_{3}^{(k)}$ 
$x_2^{k+1}$ = 1.5 - 0.75$x_{1}^{(k+1)}$ - 0.25$x_{3}^{(k)}$ 
$x_3^{k+1}$ = 0 - 0.5$x_{1}^{(k+1)}$ + 0.5$x_{2}^{(k+1)}$ 

Usando a estimativa inicial **$x^{(0)}$** = $[0 0 0]^{T}$, prosseguimos para as iterações.

**(k = 0)**

$x_1^{(1)}$  = 1 - 0 - 0 = 1
$x_2^{(1)}$  = 1.5 - 0.75(1) - 0 = 0.75
$x_3^{(1)}$  = -0.5(1) - 0.5(0.75) = -0.875

Isto é,

$x^{(1)}$ = $[1, 0.75, - 0.875]^{T}$

Para o critério de parada, computamos, primeiramente,

|$x_1^{(1)}$ - $x_1^{(0)}$| = 1
|$x_2^{(1)}$ - $x_2^{(0)}$| = 0.75
|$x_3^{(1)}$ - $x_3^{(0)}$| = 0.875

Em seguida, usamos a distância com base no erro relativo:

$d_R^{(1)}$ $=^{~}$ $1/max_{1<i<3}|x_i^{(1)}|$ = 1 > $\epsilon$

Como o critério não fora satisfeito, computamos a próxima iteração:

**(k = 1)**

$x_1^{(2)}$  = 1 - 0.2(0.75) + 0.2(0.875)  = 1.025
$x_2^{(2)}$  = 1.5 - 0.75(1.025) - 0.25(-0.875) = 0.95
$x_3^{(2)}$  = -0.5(1.025) - 0.5(0.95) = -0.9875

Isto é, 

$x^{(2)}$ = $[1.025, 0.95, - 0.9875]^{T}$

Para o critério de parada, computamos, primeiramente,

|$x_1^{(2)}$ - $x_1^{(1)}$| = 0.025
|$x_2^{(2)}$ - $x_2^{(1)}$| = 0.2
|$x_3^{(2)}$ - $x_3^{(1)}$| = 0.1125

Em seguida, usamos a distância com base no erro relativo:

$d_R^{(2)}$ $=^{~}$ $0.2/max_{1<i<3}|x_i^{(2)}|$ = 0.2/1.025 > $\epsilon$

O critério ainda não está satisfeito.

Continuando para a próxima iteração para (k = 2), teremos

  $x^{(3)}$ = $[1.0075, 0.9912, - 0.9993]^{T}$

Uma ves que $d_R^{(3)}$ = 0.0409 <$\epsilon$,

O critério de parada está satisfeito e obtemos uma aproximação para a solução do sistema dado dentro de nossa margem de erro imposta. 

Portanto, 

$x^{*}$  $={~}$ $x^{(3)}$ $=^{~}$ $[1.0075, 0.9912, - 0.9993]^{T}$

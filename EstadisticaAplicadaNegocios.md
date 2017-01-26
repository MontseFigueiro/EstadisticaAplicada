Estadística descriptiva para:

-   agrupación
-   resumen
-   presentación

Resumir y ordenar la información ayuda al análisis. Recolectar, agrupar
y presentar datos. Reduce la información lo máximo posible sin omitir
datos importantes.

La población es el universo de individuos (empresas, ciudades, paises).
Muestra es un subconjunto que se extrae de forma aleatoria y resulta
representativa de la población de interes, un parámetro es una
característica de la población.

Medidas de tendencia muestral:

-   Media, mediana y moda

Configuramos Excel con "Herramientas para análisis"

Como bajar Datos de Yahoo Finance:

En yahoo finance, en la barra de búsqueda ponemos Intel por ejemplo,
damos al botón Historical Data, indicamos el periodo de tiempo de enero
a julio 2016. Los datos pueden ser diarios, semanales o mensuales.
Download data para que se bajen en csv. Los guardaremos en formato
Excel. Usaremos la columna Adj Close que es la cotización al cierre.
Como son cotizaciones las bajamos diarias.

### Medidas de tendencia central

-   Descargamos los datos de Yahoo Finance de general Electric GE
    diarios de 4 de enero de 2016 a 22 de julio de 2016
-   Calculamos media, mediana y moda.
-   Gráfico de lineas de esta serie temporal
-   Media móvil simple de 20 periodos y gráfico, va cogiendo la media de
    las 20 observaciones anteriores para cada día.

Son estadísticos que buscan resumir en un valor la tendencia de los
datos:

Media = suma de todos los valores / n observ. Mediana= ordenamos las
observaciones de manera ascendente o descendente y cogemos el valor
central, si n es par sumamos los dos valores centrales y dividimos entre
2. En algunas situaciones la mediana puede ser preferible. Cuando hay
valores extremos éstos suben la media. Pero la mediana sigue siendo
parecido sin el valor extremo. Es una medida más robusta.

La moda es el valor más frecuente, puede suceder que no exista, que haya
más de una o que no está en el centro.

La media ponderada ponemos diferente peso a las observaciones, entre 0 y
1. (algunas calificaciones, el indice S&P 500 es un bursátil ponderado
de acuerdo a su nivel de capitalización, empresas grandes tienen más
peso)

Media Móvil, se debe determinar el número de observaciones que se
utilizarán para la observación (bandas Bollinger):

-   Media móvil simple (se suele calcular la media móvil simple de 20
    periodos, asignamos igual peso a todas las observaciones)
-   Media móvil exponencial (más peso observaciones recientes)

### MEdidas de Dispersión

Muestran la variabilidad en la distribución de los datos.

-   varianza y desviación estandar
-   coeficiente de variación
-   Rango y rango intercuartil

**varianza**:

Suma de las diferencias al cuadrado = (x-Media X)^2 / n-1 Desviación
estandar = Raiz cuadrada de la varianza

**Coeficiente de variacion**:

Para comparar la variabilidad entre dos o más conjuntos de datos con
distintas unidades de medida o distintas medias. Es la desviación
standar / media de X

**Rango o recorrido**:

Es la diferencia entre el valor máximo y mínimo de las observaciones.
Puede verse influido por algún valor extremo.

-   Rango intercuartil: Descarta el rango del 25% más alto y más bajo y
    se queda con el resto.

### Datos Agrupados.

En la práctica los datos contienen muchas observaciones que se pueden
reducir utilizando tablas de frecuencias. Muchas veces es probables que
una persona responda a una pregunta cuando se le pide que la ubique en
un rango que cuando se le pide un valor exacto.

<table>
<thead>
<tr class="header">
<th>Ingresos</th>
<th>Numero personas</th>
<th>Frec.acumulada</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>150-450</td>
<td>250</td>
<td>250</td>
</tr>
<tr class="even">
<td>450-750</td>
<td>800</td>
<td>1050</td>
</tr>
<tr class="odd">
<td>750-1050</td>
<td>1250</td>
<td>2300</td>
</tr>
</tbody>
</table>

Frecuencia es el número de observaciones de cada intervalo. Frecuencia
acumulada es el número total de observaciones que hay en ese intervalo y
los anteriores.

Frecuencia relativa: proporcion de observaciones de cada intervalo:

<table>
<thead>
<tr class="header">
<th>dias</th>
<th>empleados</th>
<th>%</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>410</td>
<td>28.5</td>
</tr>
</tbody>
</table>

LA suma de % es 100%. El histograma nos permite ver rapidamente el % de
cada intervalo.

Asimetría:

La distribución de los datos puede ser: - Simétrica: media=mediana=moda
- asimétrica a derecha (positiva): Media&gt;Mediana&gt;Moda - asimétrica
a izquierda (negativa): media<mediana<moda

Curtosis: mide el grado de concentración que presentan los valores en la región central de la distribución.

- Platicúrtica (plana)
- Leptocúrtica (estrecha)
- Mesocúrtica (normal)


###Relación entre variables

La relación lineal se puede medir con la correlación.

Diagramas de dispersión (Scatter Plot): en cada eje se pone una variable y cada punto corresponde a una observación.


```r
head(iris)
```

```
##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
## 1          5.1         3.5          1.4         0.2  setosa
## 2          4.9         3.0          1.4         0.2  setosa
## 3          4.7         3.2          1.3         0.2  setosa
## 4          4.6         3.1          1.5         0.2  setosa
## 5          5.0         3.6          1.4         0.2  setosa
## 6          5.4         3.9          1.7         0.4  setosa
```

```r
plot(iris$Sepal.Length,iris$Sepal.Width)
```

![](EstadisticaAplicadaNegocios_files/figure-markdown_strict/unnamed-chunk-1-1.png)

- Correlación positiva (creciente)
- Correlación negativa (descendiente)
- No correlación


**Coeficiente de correlación de Pearson**

Si tienen relación lineal dos variables:

Covarianza entre X e Y / (Desv.de X * Desv.de Y)

La covarianza mide el co-movimiento de dos variables respecto a su media = suma (x-mediaX)*(y- mediay)/n-1

Si covarianza > 0 dependencia lineal directa Si covarianza &lt;0
dependencia lineal inversa

Propiedades Coef.correlación:

-   Invariante al cambio de unidades, valores entre -1 y 1
-   su signo lo da la covarianza
-   los datos x e y tienden a caer en una recta
-   no cuantifica la pendiente de la recta

PROBABILIDAD
------------

La probabilidad no tiene que coincidir con la frecuencia observada. Es
la proporción de veces que el resultado se da después de una larga serie
de repeticiones del experimento.

-   espacio muestral: conjunto con todos los posibles resultados
-   evento: subconjunto de espacio muestral (sacar un as de una baraja)

La probabilidad del espacio muestral es =1 Si A y B son excluyentes P(A
U B) = P(A)+P(B) Si la P = 0 hay certeza de que ese evento no va a
ocurrir si la P = 1 hay certeza de que SI va a ocurrir ese evento.

Diagrama de Venn:

AUB: Se da A o B o la union de las dos A B: La intersección entre A y B
A-B : A pero no B ni la intersección entre A y B A^C : Se da lo que no
sea A

Ejemplo: 52 cartas A= extraer un as R=extraer un rey T=extraer un trébol

-   Probabilidad de sacar as o rey

P(asUrey)= P(as)+P(rey)= 4/52+4/52=8/52 (son excluyentes)

-   Probabilidad un as o un trébol

P(asUtrebol)= P(as)+P(trebol)-P(asytrebol)=4/52+13/52-1/52=16/52

### Probabilidad condicional e independencia

una distribución conjunta de probabilidad es aquella que permite obtener
las probabilidades de que X=x e Y=y

Si lanzamos dos dados, el primer dado es X y el segundo dado es Y, hay
36 combinaciones posibles. la probabilidad de que X=1 e Y=1 es 1/36

En el caso de los dados X e Y son **independientes** pero puede ser que
sean **dependientes**.

Ejemplo:

X= viviendas vendidas inmobiliaria A Y = "" B

Distribución conjunta:

<table>
<thead>
<tr class="header">
<th>X/Y</th>
<th>1</th>
<th>2</th>
<th>3</th>
<th>p(x)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>0.12</td>
<td>0.15</td>
<td>0.11</td>
<td>0.38</td>
</tr>
<tr class="even">
<td>2</td>
<td>0.06</td>
<td>0.23</td>
<td>0.08</td>
<td>0.37</td>
</tr>
<tr class="odd">
<td>3</td>
<td>0.03</td>
<td>0.00</td>
<td>0.22</td>
<td>0.25</td>
</tr>
<tr class="even">
<td>p(y)</td>
<td>0.21</td>
<td>0.38</td>
<td>0.41</td>
<td>1</td>
</tr>
</tbody>
</table>

Hay que demostrar que no son independientes.

Probabilidad condicional: Probabilidad de que se de B si se ha dado A

P(B/A)= P(A B)/P(A)

Regla de la probabilidad total: se da para determinal la probabilidad
incondicional de un evento.

Ejemplo: 3 proveedores A 40%, B 25% y C el resto. La probabilidad de que
sea defectuoso es producto para cada proveedor (0.001,0.005 y 0.003) La
probabilidad de que un producto sea defectuoso:

0.001*0.4+0.005*0.25+0.003\*0.35 = 0.0027

La probabilidad conjunta de dos eventos es la probabilidad de que ambos
ocurra de forma simultanea. Regla de la multiplicación de
probabilidades.

P(A B)=P(A/B)xP(B)

-   Independencia:

A y B son independientes si

P(A/B)=P(A)

P(A B)=P(A).P(B)

Teorema de Bayes. Ejemplo caso práctico.

### ÁRBOLES DE DECISIÓN

Si fertilizo:

-   700 kg si no llueve, 3300 si llueve

Si no Fertilizo:

-   1500 kg si no llueve, 2500 si llueve

E(fertilizar) = 700 x0.7 + 3300 x 0.3 = 1480 kg E(no fertilizar) = 1500
x0.7 + 2500 x 0.3 = 1800 kg Como E(no fertilizar)&gt; E(fertilizar)

NO fertilizo

**Definición**:

Técnica gráfica para representar un problema de toma de decisiones. Se
resuleve usando inducción hacia atrás en base a reglas de probabilidad y
el criterio del valor esperado.

### Variables Aleatorias

Es una variable que toma valores numéricos determinados por el resultado
de un experimento que tiene asociado una probabilidad. Se tira una
moneda al aire (experimento), definimos X como el "número de caras
obtenidas". X es una variable aleatoria que puede tomar los valores
0,1,2,3 y cada valor tiene una probabilidad asociada.

Se lanza 3 veces la moneda. X = número de caras obtenidas. Puedo obtener
0, 1, 2 o 3 caras. H =cara Las combinaciones posibles son
HHH,HHT,HTH,THH,HTT,THT,TTH,TTT

La tabla de probabilidades es:

<table>
<thead>
<tr class="header">
<th>X</th>
<th>P(X)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>1/8=0.125</td>
</tr>
<tr class="even">
<td>1</td>
<td>3/8=0.375</td>
</tr>
<tr class="odd">
<td>2</td>
<td>3/8=0.375</td>
</tr>
<tr class="even">
<td>3</td>
<td>1/8=0.125</td>
</tr>
</tbody>
</table>

Pueden ser:

-   categóricas
    -   Nominales: sexo, raza
    -   Ordinales: nivel educativo
-   Numéricas
    -   Discretas: numero de hijos, edad
    -   Coninuas: ingreso, altura

#### Variables Aleatorias Discretas

Un ejemplo es lanzar un dado, X es la variable aleatoria que indica el
número resultante. P(X=1)=1/6

LA probabilidad de que X sea igual o mayor que 2 e igual o menor que 4
significa que puede ser 2,3,4 esto es 3/6 Probabilidad de que X sea
igual o menor que 5 es 5/6

Son las sumas de las probabilidades.

**VALOR ESPERADO** o Esperanza Matemática

Es una medida de lo que ocurre con más frecuencia.

    \( \mu \ M \) = E(X)= p1x1+p2x2....

Ejemplo:

<table>
<thead>
<tr class="header">
<th>X</th>
<th>P(X=x)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>0,30</td>
</tr>
<tr class="even">
<td>1</td>
<td>0,27</td>
</tr>
<tr class="odd">
<td>2</td>
<td>0,20</td>
</tr>
<tr class="even">
<td>3</td>
<td>0,13</td>
</tr>
</tbody>
</table>

Cantidad de autos que compra una familia en el lapso de 5 años,
conocemos la probabilidad asociada a cada x.

El valor esperado es:

    VE <- (0*0.30+1*0.27+2*0.20+3*0.13)
    VE

    ## [1] 1.06

El valor esperado es que en cinco años se compren un coche de media.

Propiedades de la esperanza:

-   Si tenemos dos variables aleatorias X e Y
    -   E(X+Y)=E(X)+E(Y)
    -   E(X-Y)=E(X)-E(Y)

**VARIANZA**

No podemos limitarnos a medidas de tendencia central como la media, no
tendríamos idea de como se distribuyen los datos. Calculamos la varianza
como medida de dispersión.

Si X es discreta:

Varianza = (X-E(X))^2

Es un promedio ponderado por su probabilidad de la distancia cuadrática
entre la media y cada x. Es mayor cuanto más lejos estén los x de la
media y cuanto mayor sea el peso (ocurrencia) de esos valores.

En el ejemplo anterior de los coches:

<table>
<thead>
<tr class="header">
<th>X</th>
<th>P(X)</th>
<th>x-mu</th>
<th>(x-mu)^2</th>
<th>(x-mu)^2*P(x)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>0</td>
<td>0.30</td>
<td>0-1.51</td>
<td>2.28</td>
<td>2.28*0.30=0.68</td>
</tr>
</tbody>
</table>

La suma de la última columna es 2.03

    valores <- c(0,1,2,3,4,5,6)
    probabilidades <- c(0.30,0.27,0.20,0.13,0.06,0.03,0.01)
    tabla <- data.frame(valores,probabilidades)
    media <- sum(tabla$valores*tabla$probabilidades)
    tabla$esperanza <- tabla$valores*tabla$probabilidades
    tabla$var <- (tabla$valores-media)^2
    var <- sum(tabla$var*tabla$probabilidades)
    var

    ## [1] 2.0299

Propiedades de la Varianza:

V(X+-Y)=V(X)+-V(Y)+-2COV(X,Y) son dependientes V(X+-Y)=V(X)+V(Y) si son
independientes COV(X,Y)=0

**COVARIANZA**

Es una medida de asociación entre dos variables aleatorias X e Y.

COV(X,Y)= E\[(X-mux)(Y-muY)\]= SUMA ((x-mu)(y-mu)p(x,y))

Hay que conocer la probabilidad conjunta. Una covarianza positiva
implica una asociación lineal positiva.

> 0 si sube X sube Y &lt;0 si sube X baja Y =0 no hay relacion

Las variables son independientes si:

p(x,y)=p(x).p(y) cov(X,Y)=0

**CORRELACIÓN**

La covarianza depende de las unidades de medición. Muchas veces
utilizamos el coeficiente de correlación.

COV(X,Y)/varianza(X)\*varianza(Y)

Mantiene el signo de la covarianza, es 0 cuando la covarianza es 0.

Su valor va desde -1 a 1. Es una medida muy utilizada en la práctica.

-   Correlación positiva perfecta 1
-   Correlacion negativa perfecta -1
-   correlación 0
-   Fuerte asociacion no lineal (la distribución es polinomica)

### Distribución Binomial

Una distribucion de probabilidad es aquella función que asigna una
probabilidad a cada posible valor de una variable aleatoria. La binomial
es muy usual en variables aleatorias discretas.

Probabilidades Binomiales:

Lanzamos una moneda tres veces, cual es la probabilidad de sacar una
cara:

H cara T cruz

HHH HTH HHT THH HTT THT TTH TTT

    P_una_cara <- 1/8+1/8+1/8
    P_una_cara

    ## [1] 0.375

Y la probabilidad de sacar una cara cuando se lanzan 100 veces una
moneda??

-   Un experimento aleatorio arroja dos resultados, exito(p)
    o fracaso(1-p)
-   Se llevan a cabo n repeticiones independientes del experimento
-   La distribución de éxitos X se conoce como distribución binomial:
-   E(X)=n.p y V(X)=n.p(1-p)

dbinom(x, size, prob) pbinom(x, size, prob) qbinom(p, size, prob)
rbinom(n, size, prob)

**pbinom** Probabilidad de sacar 26 o mnenos caras al lanzar 51 veces
una moneda

    x <- pbinom(26,51,0.5)
    x

    ## [1] 0.610116

**dbinom** Da la densidad de la distribución en cada punto

    x <- seq(0,50,by=1)
    y <- dbinom(x,50,0.5)
    plot(x,y)

![](EstadisticaAplicadaNegocios_files/figure-markdown_strict/unnamed-chunk-6-1.png)
**qbinom** Toma la probabilidad y nos da un número de tiradas.

Cuantas caras tienen una probabilidad de 25% de salir cuando lanzamos la
moneda 51 veces.

    x <- qbinom(0.25,51,1/2)
    x

    ## [1] 23

**rbinom** Genera un número aleatorio de valores dado una probabilidad

Encontrar 8 valores aleatorios de un ejemplo de 150 con una probabilidad
de 0.4

    x <- rbinom(8,150,.4)
    x

    ## [1] 66 61 60 57 68 53 59 64

Ejemplo:

Un exámen final consta de 10 preguntas multiple respuesta (4 opciones
cada una), solo una respuesta es correcta. Cual es la probabilidad de
acertar 5 preguntas o más al azar.

Tengo la probabilidad de éxito para cada pregunta que es 1/4, el número
de lanzamientos es 10 y quiero 5 o más éxitos. LA probabilidad de sacar
4 o menos éxitos:

    x <- pbinom(4,10,1/4)
    x

    ## [1] 0.9218731

    inversa <- 1-x
    round(inversa,2)

    ## [1] 0.08

### Distribución Normal

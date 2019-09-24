# Busqueda de moda

#### Lo que se busca
Dado un array ordenada, se quiere buscar la moda, en caso de haber dos números modales, dejar aquel que se hayá obtenido último

#### Algoritmo (Conteo de ocurrencias)
Se recorre el arreglo de manera lineal contando la cantidad de ocurrencias de cada número.  
Para ello se cuenta con 4 variables extras, una con el número que se esta verificando, otra con la cuenta o cantidad de ocurrencias contadas, otra con el número mayor actualmente, y otra con la cuenta del número mayor que se tiene hasta el momento.
Por lo tanto, se empieza con el primer número, el cual pasa a tener una cuenta de sus ocurrencias, y se recorre la lista, donde si el siguiente es igual al número anterior, se le agrega una ocurrencia y se pasa al siguiente, y así sucesivamente. En caso de ser distintos, se verifica la cuenta con la cantidad de ocurrencias del número mayor actual, y si es mayor se cambia la "moda" actual. Independiente si se consigue una nueva "moda" o no, al pasar al número siguiente se vuelve el contador 0.  
Una vez terminado de recorrer el arreglo, se procede a guardar la moda en la variable pedida, y se dejan los demás registros en 0.

#### Pseudocódigo

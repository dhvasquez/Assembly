# Busqueda de moda

#### Lo que se busca
Dado un array ordenada, se quiere buscar la moda, en caso de haber dos números modales, dejar aquel que se hayá obtenido último

#### Algoritmo (Conteo de ocurrencias)
Se recorre el arreglo de manera lineal contando la cantidad de ocurrencias de cada número.  
Para ello se cuenta con 4 variables extras, una con el número que se esta verificando, otra con la cuenta o cantidad de ocurrencias contadas, otra con el número mayor actualmente, y otra con la cuenta del número mayor que se tiene hasta el momento.
Por lo tanto, se empieza con el primer número, el cual pasa a tener una cuenta de sus ocurrencias, y se recorre la lista, donde si el siguiente es igual al número anterior, se le agrega una ocurrencia y se pasa al siguiente, y así sucesivamente. En caso de ser distintos, se verifica la cuenta con la cantidad de ocurrencias del número mayor actual, y si es mayor se cambia la "moda" actual. Independiente si se consigue una nueva "moda" o no, al pasar al número siguiente se vuelve el contador 0.  
Una vez terminado de recorrer el arreglo, se procede a guardar la moda en la variable pedida, y se dejan los demás registros en 0.

#### Pseudocódigo
Lo que se realiza es empezar con el primer dato del arreglo, se le agrega como la moda actual, y se la agrega uno a su contador.  
Luego se avanza en el arreglo, y se compara con el anterior (Para poder realizar la comparación se realiza un push a memoria).  
Si el siguiente es igual al anterior, se le agrega uno al contador, si no son iguales, se pasa al siguiente y se reinicia el contador.  
Antes de reinciar el contador se comparan las cuentas, y si la cuenta del número actual es mayor o igual al anterior, se cambia la moda.  
Finalmente, al terminar de recorrer el arreglo se traspasa el número con más conteo a la moda final.

##### Representación en Python 3.6.8
```python
# Definimos el arreglo y su largo
arreglo = [
    -35, -35, -30, -29, -28, -26, -16, -5, 15,
    23, 26, 26, 28, 31, 31, 35, 40, 44, 51, 55
]
largo_arreglo = len(arreglo)
resultado = 0
# Definimos las variables auxiliares
verificando = 0
cuenta = 0
mayor = 0
cuenta_mayor = 0

# Traspasamos el primer número
verificando = arreglo[0]
cuenta = 1
mayor = arreglo[0]
cuenta_mayor = 1
# Empezamos el conteo
for i in range(1, largo_arreglo):
    if verificando == arreglo[i]:  # Se verifica que el siguiente sea igual
        cuenta += 1
        verificando = arreglo[i]
    else:
        if cuenta >= cuenta_mayor:  # Nos quedamos con la moda más reciente
            mayor = verificando
            cuenta_mayor = cuenta
        # Pasamos al siguiente y le agregamos una cuenta
        verificando = arreglo[i]
        cuenta = 1  # Le agregamos uno a la cuenta del siguiente

resultado = mayor
print(resultado)
```
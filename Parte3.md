# Orden de arreglos

## Nombre: Diego Hao-Hai Vásquez Thio
## N° Alumno: 17642566

#### Lo que se busca
Dado una cantidad de arreglos, y sus respectivos largos, se busca ordenar de menor a mayor cada uno de los arreglos de manera independiente, es decir, ordenar un arreglo, luego el siguiente, y así sucesivamente.

#### Algoritmo (Bubble Sort)
Lo que realiza el agoritmo escrito es recorrer el arreglo, y comparar el valor actual con el siguiente. Si el valor actual es menor, se pasa al siguiente número. Si el valor actual es mayor al siguiente, se intercambian, y se le suma 1 a un contador, luego se pasa al siguiente.  
Una vez terminado de recorrer el arreglo, se revisa el contador de veces que se intercambiaron resultados, si es mayor a 0, se devuelve el valor del contador a 0 y se vuelve a recorrer el arreglo realizando intercambios. En caso de ser 0, se pasa al siguiente arreglo y se realiza lo mismo hasta que no queden arreglos para ordenar.  
Cabe destacar que cada vez que se recorre un segundo (o mayor) arreglo, se vuelve a comprobar el primer arreglo, y asi sucesivamente.  

#### Pseudocódigo
Se llama a la subrutina donde se empieza a comparar cada elemento del arreglo con el siguiente, esto se logra con ayuda de 2 variables auxiliares y un contador, ya que cada vez que se realiza un intercambio, se le suma 1 al contador, y se repite el proceso de intercambio hasta que ese contador sea 0. Pasando así a ordenar el siguiente arreglo, pero cada vez que se empieza a revisar un segundo arreglo se revisa igualmente los arreglos anteriores, pero al estar ordenados siempre su contador sera 0.

##### Representación en Python 3.6.8
```python
def bubble_sort(arreglo, largo):
    """
    Algoritmo que hace bubble sort mediante un loop hasta que no ocurran
    intercambios entre valores
    """
    while True:
        # Variables auxiliares
        aux_1 = 0
        aux_2 = 0
        contador = 0
        # Llamamos a los arreglos
        arreglo = arreglo
        largo = largo
        for i in range(largo - 1):
            if arreglo[i] > arreglo[i + 1]:  # Realizamos los intercambios
                aux_1 = arreglo[i]
                aux_2 = arreglo[i + 1]
                arreglo[i] = aux_2
                arreglo[i + 1] = aux_1
                # Contamos los intercambios
                contador += 1
        if contador == 0:
            # Paramos el loop en caso de que no ocurran intercambios
            break
    return arreglo


# Definimos los arreglos que queremos ordenar
arreglo_1 = [
    5, 3, -3, 2, -7, 18, 7, -1, 20, -30, 20, -33, 55, -19, 60, -18, 53, 12, 5
]

largo_arreglo_1 = len(arreglo_1)
# Cambiamos el arreglo
arreglo_1 = bubble_sort(arreglo_1, largo_arreglo_1)
# Agregamos los arreglos que queremos ordenar
print(arreglo_1)
```
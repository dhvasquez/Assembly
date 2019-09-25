# Suma de números de 16 bits en Big Endian

## Nombre: Diego Hao-Hai Vásquez Thio
## N° Alumno: 17642566

#### Big Endian
Los números en Big Endian permiten dividir números en bytes, y escribirlos de izquierda a derecha, donde se empieza con el más significativo, y se termina con el menos significativo.

#### Algoritmo (Suma de menos significativo a más significativo)
Lo que realiza este algoritmo es sumar primero lás partes menos significativas del número (en big endian), guardarlas en una variable auxiliar, y luego sumar los números más significativos y guardarlos en otra variable.  
Una vez realizado lo anterior se procede a comparar la variable auxiliar más significativa con 0, viendo si es mayor, menor o igual, y proceder a guardarla en las variables pedidas, que también están en formato big endian.

#### Pseudocódigo
En primer lugar, direcciona las partes del número menos significativas a los registros A y B, donde A es el byte menos significativo del primer número (num_1_2), y B es el byte menos significativo del segundo número (num_2_2).  
Luego se suman ambos registros, y su resultado se guarda en la variable aux_2, siendo esta la parte menos significativa del nuevo número.  
Luego se direccionan las partes más significativas de cada número (num_1_1 y num_2_1) a los registro A y B, respectivamente.  
Se suman ambos registros, y su resultado se guarda en la variable aux_1.  
Finalmente se direccionan aux_1 y aux_2 a A y B respectivamente, se compara A con 0, y si es mayor a 0, se guarda aux_1 y aux_2 en la variable res_a y res_b. En caso de ser menor a 0, se guarda aux_1 y aux_2 en res_c y res_d.  

##### Representación en Python 3.6.8
```python
# Definimos los números
num_1_1 = 120
num_1_2 = 34
num_2_1 = 0
num_2_2 = -1

# Definimos las variables que guardan los resultados
res_a = 0
res_b = 0
res_c = 0
res_d = 0

# Definimos las variables auxiliares
aux_1 = 0
aux_2 = 0

# Empezamos, definimos las variables menos significativas a los 
# registros A y B y sumamos
A = num_1_2
B = num_2_2
A = A + B
aux_2 = A

# Realizamos los mismo para los números más significativos
A = num_1_1
B = num_2_1
A = A + B
aux_1 = A

# Comparamos el auxiliar más significativo con 0
if aux_1 < 0:
    res_c = aux_1
    res_d = aux_2
    print("Menor a 0:")
    print(res_c)
    print(res_d)
else:
    res_a = aux_1
    res_b = aux_2
    print("Mayor o igual a 0:")
    print(res_a)
    print(res_b)
```
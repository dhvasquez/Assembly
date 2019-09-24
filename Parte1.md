# Suma de números de 16 bits en Big Endian

#### Big Endian
Los números en Big Endian permiten dividir números en bytes, y escribirlos de izquierda a derecha, donde se empieza con el más significativo, y se termina con el menos significativo.

#### Algoritmo (Suma de menos significativo a más significativo)
Lo que realiza este algoritmo es sumar primero lás partes menos significativas del número (en big endian), guardarlas en una variable auxiliar, y luego sumar los números más significativos y guardarlos en otra variable.  
Una vez realizado lo anterior se procede a comparar la variable auxiliar más significativa con 0, viendo si es mayor, menor o igual, y proceder a guardarla en las variables pedidas, que también están en formato big endian.

#### Pseudocódigo
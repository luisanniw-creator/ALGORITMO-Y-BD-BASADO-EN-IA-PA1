# Actividad 3: Matrices y recorrido completo de datos

## 3.1 Matriz propuesta

La institución registra la ocupación de aulas mediante una matriz de 4 filas por 5 columnas.

- Filas = Aulas
- Columnas = Bloques horarios
- Cada celda representa la cantidad de estudiantes en un aula y horario determinado.

### Matriz propuesta

|        | Horario 1 | Horario 2 | Horario 3 | Horario 4 | Horario 5 |
|--------|-----------|-----------|-----------|-----------|-----------|
| Aula 1 | 20        | 15        | 30        | 25        | 18        |
| Aula 2 | 12        | 28        | 22        | 35        | 16        |
| Aula 3 | 25        | 18        | 32        | 20        | 27        |
| Aula 4 | 10        | 24        | 19        | 30        | 14        |

Total de celdas: 4 × 5 = 20.

### Código Java

```java
int[][] ocupacion = {
    {20, 15, 30, 25, 18},
    {12, 28, 22, 35, 16},
    {25, 18, 32, 20, 27},
    {10, 24, 19, 30, 14}
};

--

3.2 Filas, columnas e índices

La matriz utiliza índices que comienzan desde 0.

Filas
Fila 0 = Aula 1
Fila 1 = Aula 2
Fila 2 = Aula 3
Fila 3 = Aula 4
Columnas
Columna 0 = Horario 1
Columna 1 = Horario 2
Columna 2 = Horario 3
Columna 3 = Horario 4
Columna 4 = Horario 5

Para acceder a una posición se utiliza:

ocupacion[fila][columna]

Por ejemplo:

ocupacion[1][3] = 35

Corresponde al Aula 2, Horario 4.

--

3.3 Total de estudiantes por aula

Para calcular el total de estudiantes de cada aula se recorre cada fila de la matriz y se suman sus valores.

Pseudocódigo
PARA i = 0 HASTA filas - 1 HACER
    totalAula ← 0

    PARA j = 0 HASTA columnas - 1 HACER
        totalAula ← totalAula + matriz[i][j]
    FIN PARA

    IMPRIMIR total del Aula
FIN PARA
Resultados
Aula 1: 108 estudiantes
Aula 2: 113 estudiantes
Aula 3: 122 estudiantes
Aula 4: 97 estudiantes
Código Java
for (int i = 0; i < ocupacion.length; i++) {
    int totalAula = 0;

    for (int j = 0; j < ocupacion[i].length; j++) {
        totalAula = totalAula + ocupacion[i][j];
    }

    System.out.println("Total del Aula " + (i + 1) + ": " + totalAula);
}

--
3.4 Total de estudiantes por horario

Para calcular el total de estudiantes de cada horario se recorre cada columna de la matriz y se suman sus valores.

Pseudocódigo
PARA j = 0 HASTA columnas - 1 HACER
    totalHorario ← 0

    PARA i = 0 HASTA filas - 1 HACER
        totalHorario ← totalHorario + matriz[i][j]
    FIN PARA

    IMPRIMIR total del Horario
FIN PARA
Resultados
Horario 1: 67 estudiantes
Horario 2: 85 estudiantes
Horario 3: 103 estudiantes
Horario 4: 110 estudiantes
Horario 5: 75 estudiantes
Código Java
for (int j = 0; j < ocupacion[0].length; j++) {
    int totalHorario = 0;

    for (int i = 0; i < ocupacion.length; i++) {
        totalHorario = totalHorario + ocupacion[i][j];
    }

    System.out.println("Total del Horario " + (j + 1) + ": " + totalHorario);
}

--
3.5 Identificación de la celda con mayor ocupación

Para identificar la celda con mayor ocupación se recorren todas las posiciones de la matriz y se compara cada valor con el mayor encontrado hasta ese momento.

Pseudocódigo
mayor ← matriz[0][0]
aulaMayor ← 0
horarioMayor ← 0

PARA i = 0 HASTA filas - 1 HACER
    PARA j = 0 HASTA columnas - 1 HACER

        SI matriz[i][j] > mayor ENTONCES
            mayor ← matriz[i][j]
            aulaMayor ← i
            horarioMayor ← j
        FIN SI

    FIN PARA
FIN PARA

IMPRIMIR mayor
IMPRIMIR aulaMayor
IMPRIMIR horarioMayor
Resultado
Mayor ocupación: 35 estudiantes
Índice: [1][3]
Ubicación: Aula 2, Horario 4
Código Java
int mayor = ocupacion[0][0];
int aulaMayor = 0;
int horarioMayor = 0;

for (int i = 0; i < ocupacion.length; i++) {
    for (int j = 0; j < ocupacion[i].length; j++) {

        if (ocupacion[i][j] > mayor) {
            mayor = ocupacion[i][j];
            aulaMayor = i;
            horarioMayor = j;
        }
    }
}

System.out.println("Mayor ocupacion: " + mayor + " estudiantes");
System.out.println("Indice de la celda: [" + aulaMayor + "][" + horarioMayor + "]");
System.out.println("Ubicacion: Aula " + (aulaMayor + 1)
        + ", Horario " + (horarioMayor + 1));

--
3.6 Recorrido de la matriz

La actividad requiere recorrer varias posiciones de la matriz porque los resultados solicitados dependen de diferentes elementos.

Se utilizan dos ciclos for anidados:

El ciclo externo recorre las filas, que representan las aulas.
El ciclo interno recorre las columnas, que representan los bloques horarios.

Este recorrido permite:

Calcular el total de estudiantes por aula.
Calcular el total de estudiantes por horario.
Comparar las posiciones para identificar la celda con mayor ocupación.

El patrón general de recorrido es:

for (int i = 0; i < ocupacion.length; i++) {
    for (int j = 0; j < ocupacion[i].length; j++) {
        // Procesar ocupacion[i][j]
    }
}





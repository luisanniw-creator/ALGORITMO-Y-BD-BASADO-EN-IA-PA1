# Actividad 3: Matrices y Recorrido Completo de Datos

## 1. Matriz de ocupación

La matriz representa la cantidad de estudiantes en 4 aulas durante 5 bloques horarios.

|    | H1 | H2 | H3 | H4 | H5 |
| -- | -: | -: | -: | -: | -: |
| A1 | 20 | 15 | 30 | 25 | 18 |
| A2 | 12 | 28 | 22 | 35 | 16 |
| A3 | 25 | 18 | 32 | 20 | 27 |
| A4 | 10 | 24 | 19 | 30 | 14 |

La matriz tiene:

**4 × 5 = 20 posiciones**

### Código Java

```java
int[][] ocupacion = {
    {20, 15, 30, 25, 18},
    {12, 28, 22, 35, 16},
    {25, 18, 32, 20, 27},
    {10, 24, 19, 30, 14}
};
```

## 2. Total de estudiantes por aula

Para obtener el total de cada aula se recorren las filas y se suman sus valores.

| Aula | Total |
| ---- | ----: |
| A1   |   108 |
| A2   |   113 |
| A3   |   122 |
| A4   |    97 |

### Código Java

```java
for (int i = 0; i < ocupacion.length; i++) {

    int totalAula = 0;

    for (int j = 0; j < ocupacion[i].length; j++) {
        totalAula += ocupacion[i][j];
    }

    System.out.println("Total del Aula " + (i + 1) + ": " + totalAula);
}
```

## 3. Total de estudiantes por horario

Para obtener el total de cada horario se recorren las columnas y se suman sus valores.

| Horario | Total |
| ------- | ----: |
| H1      |    67 |
| H2      |    85 |
| H3      |   103 |
| H4      |   110 |
| H5      |    75 |

### Código Java

```java
for (int j = 0; j < ocupacion[0].length; j++) {

    int totalHorario = 0;

    for (int i = 0; i < ocupacion.length; i++) {
        totalHorario += ocupacion[i][j];
    }

    System.out.println("Total del Horario " + (j + 1) + ": " + totalHorario);
}
```

## 4. Celda con mayor ocupación

Se recorren todas las posiciones para encontrar el valor más alto.

La mayor ocupación es de **35 estudiantes**.

Se encuentra en:

* **Aula:** 2
* **Horario:** 4
* **Índice:** `[1][3]`

### Código Java

```java
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
System.out.println("Indice: [" + aulaMayor + "][" + horarioMayor + "]");
System.out.println("Aula " + (aulaMayor + 1) +
                   ", Horario " + (horarioMayor + 1));
```

## 5. Recorrido completo de la matriz

Para recorrer toda la matriz se utilizan dos ciclos `for`.

```java
for (int i = 0; i < ocupacion.length; i++) {

    for (int j = 0; j < ocupacion[i].length; j++) {

        System.out.println(ocupacion[i][j]);
    }
}
```

El primer ciclo recorre las **filas** y el segundo recorre las **columnas**.

De esta manera se pueden revisar, sumar y comparar todos los datos de la matriz.

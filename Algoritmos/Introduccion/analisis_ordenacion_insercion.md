# Análisis de la Ordenación por Inserción

**¿Cuanto tiempo tarde el procedimiento INSERTION-SORT?**

Una forma de averiguarlo es ejecutarlo en tu ordenador y cronometrarlo.

**¿Qué tipo de información te proporcionaria esta prueba de tiempo de este tipo?**

Tiempo exacto en tu ordenador, con esa entrada especifica con:

- Compilador o interprete especifico que utilizaste
- Tareas de segundo plano de tu sistema operativo

**¿Qué pasaria si lo ejecutamos con otra entrada o en un ordenador diferente?**

No mucho

Por lo que en lugar de cronometrar una o varias ejecuciones, podemos determinar su tiempo analizando el algoritmo en sí mismo.

- Examinaremos cuantas veces se ejecuta cada lina del pseudocódigo
- Cuanto tiempo tarda cada linea en ejecutarse

Desarrollaremos una formula precisa, aunque compleja para calcular el tiempo de ejecución. Luego simplificaremos la parte importante de la formula utilizando una notación práctica que nos permita comparar los tiempo de ejecución de diferentes algoritmos para el mismo problema

**¿Como analizaremos la ordenación por inserción?**

- Primero reconocer que el tiempo de ejecución dependerá de la entrada
- Las medidas de tiempo pueden variar si al ordenar dos matrices del mismo tamaño una esta mas ordenada que otra.

Aunque el tiempo de ejecución puede depender de muchas caracteristicas de la entrada, nos enfocaremos 
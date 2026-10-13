# Práctica 1 · La serie de Maclaurin y el criterio de paro

**UEA 1151039 · Métodos Numéricos en Ingeniería · Trimestre 26-O · UAM Azcapotzalco**
**Profesor:** M. en C. Gabriel Hurtado Avilés

| | |
|---|---|
| Equipo | |
| Integrantes (nombre, matrícula y licenciatura) | Cazares Gonzalez Kevin Uriel 2242002000 Ing Civil |
| Repositorio de la Tarea 1 de | Cazares Gonzalez Kevin Uriel |
| Fecha | 12/10/2026 |

## 1. Octave y Python

![Octave](img/01-octave.png)
<img width="1102" height="623" alt="Captura de pantalla 2026-10-12 194009" src="https://github.com/user-attachments/assets/3676b028-939b-4332-98e2-5b15533e10a8" />

![Python](img/02-python.png)
<img width="1115" height="628" alt="Captura de pantalla 2026-10-12 194102" src="https://github.com/user-attachments/assets/b4daf15e-ad99-4bd7-a7d8-414fc99f7e43" />

¿Coinciden con la lámina 25 de la unidad I?

###Si

## 2. Las dos líneas que completamos en `maclaurin.c`

```c
/* termino = termino * X / n; */
/* ea = fabs((aprox - anterior) / aprox) * 100.0; */
Nota: Le agregue una f al segundo código en abs
```

![C](img/03-c.png)
<img width="1095" height="596" alt="Captura de pantalla 2026-10-12 201134" src="https://github.com/user-attachments/assets/339a404d-4570-4348-9e80-55c7082444c1" />


## 3. Más cifras significativas

| Cifras | εs (%) | Términos | Aproximación | Error verdadero (%) |
|---|---|---|---|---|
| 3 | 0.0157953 | 6 |  1.648697916666667 | 0.00141649 |
| 6 | 5.87614e-06 | 9 | 1.648721265035962 | 3.43549e-07 |
| 17 | 0 | 16 | 1.648721270700128 | 2.69354e-14 |

1. ¿Cuántos términos hacen falta en cada caso? R= 6 en el primer caso, 9 en el segundo y 16 en el tercero
2. En cada fila de la tabla, ¿εa es mayor o menor que εt? ¿Por qué conviene detenerse con εa? R= es mayor εt, por lo infimos que se vuelven los números
3. Con 17 cifras el programa termina. ¿Cuántas cifras del resultado son correctas en realidad? R= 16
   Relaciónenlo con 0.1 + 0.2 de la Tarea 1.

## Uso de inteligencia artificial

Ninguno / Cuál y para qué.

Ninguna

## Referencias
-Chapra, S. C., & Canale, R. P. (2015). Métodos Numéricos para Ingenieros (7a ed.). McGraw-Hill. Capítulo 3,
ejemplo 3.2, y capítulo 4.

-Burden, R. L., & Faires, J. D. (2011). Análisis Numérico (9a ed.). Cengage Learning. Capítulo 1.

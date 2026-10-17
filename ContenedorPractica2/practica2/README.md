# Práctica 2 · Raíces de ecuaciones no lineales

**UEA 1151039 · Métodos Numéricos en Ingeniería · Trimestre 26-O · UAM Azcapotzalco**
**Profesor:** M. en C. Gabriel Hurtado Avilés

| | |
|---|---|
| Equipo | |
| Integrantes (nombre, matrícula y licenciatura) | Cazares Gonzalez Kevin Uriel 2242002000 Ing. Civil|
| Ecuación asignada| 4. Deflexión máxima de una viga |
| Fecha | 16/10/2026 |

---

## 1. Octave y Python con el paracaidista

Capturas de `octave raices.m` y de `python3 raices.py` sin cambiar nada. Sus tablas
coinciden con las de las láminas de la unidad II.

![Octave](img/01-octave.png)

<img width="1234" height="845" alt="Captura de pantalla 2026-10-15 192637" src="https://github.com/user-attachments/assets/aafd189a-7e80-4753-8e1d-57c5903bd02c" />
<img width="1095" height="847" alt="Captura de pantalla 2026-10-15 192650" src="https://github.com/user-attachments/assets/2fda6ff6-a77b-474b-b375-af492c95f318" />

![Python](img/02-python.png)

<img width="1024" height="839" alt="Captura de pantalla 2026-10-15 192701" src="https://github.com/user-attachments/assets/590b90bd-1ca4-48e1-bd8c-2695a3d0d0b3" />

## 2. Las cinco líneas que completamos en `raices.c`

```c
/* fabs((nuevo - anterior) / nuevo) * 100.0; */
/* x = b - f(b) * (a - b) / (f(a) - f(b)); */
/* x_nuevo = g(x); */
/* x - f(x) / fp(x); */
/* x - delta * f(x) / (f(x + delta) - f(x)); */
```

![Compilación](img/03-c-compilacion.png)
![Ejecución en C](img/04-c-ejecucion.png)

<img width="1099" height="847" alt="Captura de pantalla 2026-10-15 194551" src="https://github.com/user-attachments/assets/5cfd8297-4f23-4c1f-84f0-a4576e792922" />
<img width="793" height="329" alt="Captura de pantalla 2026-10-15 194602" src="https://github.com/user-attachments/assets/17849043-9c77-47ee-ad75-920243e6e15d" />


¿Coinciden las tablas de C con las de Octave y Python? Sí / No, y en qué. Si 

## 3. Las gráficas de Python

![Función](img/funcion.png)
![Convergencia](img/convergencia.png)

<img width="1000" height="600" alt="funcion" src="https://github.com/user-attachments/assets/d2a050ee-dbf5-4491-b2d9-aa1e26bc3170" />


## 4. Nuestra ecuación

| | |
|---|---|
| f(x) | −5x⁴ + 6L²x² − L⁴|
| f'(x) | -20x³ + 12L²x + 12x²L - 4L³|
| g(x) | √((5x⁴ + L⁴) / (6L²)) |
| Intervalo [a, b] | [0, 400] |
| x₀ y δ | x₀ = 200 · δ = 0.05 |
| Tolerancia | εa ≤ 0.5 % |

![C con nuestra ecuación](img/05-c-ecuacion.png)

<img width="783" height="751" alt="Captura de pantalla 2026-10-16 222420" src="https://github.com/user-attachments/assets/4ce1d17f-5083-45db-8c84-8c7b385f0894" />
<img width="798" height="653" alt="Captura de pantalla 2026-10-16 222428" src="https://github.com/user-attachments/assets/06c7d879-f16a-4af1-9de4-2fde787f8e8d" />

![Python con nuestra ecuación](img/06-python-ecuacion.png)

<img width="846" height="839" alt="Captura de pantalla 2026-10-16 223753" src="https://github.com/user-attachments/assets/55c4d32f-8506-4675-a78e-0080462c69e0" />
<img width="688" height="639" alt="Captura de pantalla 2026-10-16 223804" src="https://github.com/user-attachments/assets/216b0afb-449d-4983-b597-cea39336026c" />


### Tablas (salida de C)

**Bisección**

| k | a | b | x | f(x) | εa (%) |
|---|---|---|---|---|---|
| 1 | 0.000000 | 400.000000 | 200.000000 | -5.120000e+10 | - |
| 2 | 200.000000 | 400.000000 | 300.000000 | 2.430000e+10 | 33.3333 |
| 3 | 200.000000 | 300.000000 | 250.000000 | -1.413125e+10 | 20.0000 |
| 4 | 250.000000 | 300.000000 | 275.000000 | 5.154297e+09 | 9.0909 |
| 5 | 250.000000 | 275.000000 | 262.500000 | -4.502856e+09 | 4.7619 |
| 6 | 262.500000 | 275.000000 | 268.750000 | 3.259933e+08 | 2.3256 |
| 7 | 262.500000 | 268.750000 | 265.625000 | -2.088854e+09 | 1.1765 |
| 8 | 265.625000 | 268.750000 | 267.187500 | -8.814750e+08 | 0.5848 |
| 9 | 267.187500 | 268.750000 | 267.968750 | -2.777444e+08 | 0.2915 |

**Falsa posición**

| k | a | b | x | f(x) | εa (%) |
|---|---|---|---|---|---|
| 1 | 0.000000 | 400.000000 | 238.235294 | -2.311317e+10 | - |
| 2 | 238.235294 | 400.000000 | 271.884726 | 2.748221e+09 | 12.3764 |
| 3 | 238.235294 | 271.884726 | 268.308891 | -1.488905e+07 | 1.3327 |
| 4 | 268.308891 | 271.884726 | 268.328159 | 1.305217e+03 | 0.0072 |

**Punto fijo**

| k | x | f(x) | εa (%) |
|---|---|---|---|
| 0 | 200.000000 | -5.120000e+10 | - |
| 1 | 252.395926 | -1.229081e+10 | 20.7594 |
| 2 | 263.427207 | -3.786753e+09 | 4.1876 |
| 3 | 266.733986 | -1.231930e+09 | 1.2397 |
| 4 | 267.800966 | -4.074048e+08 | 0.3984 |

**Newton-Raphson**

| k | x | f(x) | εa (%) |
|---|---|---|---|
| 0 | 200.000000 | -5.120000e+10 | - |
| 1 | 272.727273 | 3.399112e+09 | 26.6667 |
| 2 | 268.326967 | -9.197298e+05 | 1.6399 |
| 3 | 268.328157 | 1.525879e-05 | 0.0004 |

**Secante modificada**

| k | x | f(x) | εa (%) |
|---|---|---|---|
| 0 | 200.000000 | -5.120000e+10 | - |
| 1 | 272.722315 | 3.395283e+09 | 26.6653 |
| 2 | 268.326951 | -9.323579e+05 | 1.6381 |
| 3 | 268.328157 | 1.506042e-02 | 0.0004 |

Agreguen las filas que hagan falta.

### Resumen

| Método | Raíz | Iteraciones | εa (%) | f(raíz) | Error verdadero (%) |
|---|---|---|---|---|---|
| Bisección | 267.968750 | 9 | 0.2915 | -2.777444e+08 |
| Falsa posición | 268.328159 | 4 | 0.0072 | 1.305217e+03 |
| Punto fijo | 267.800966 | 4 | 0.3984 | -4.074048e+08 |
| Newton-Raphson | 268.328157 | 3 | 0.0004 | 1.525879e-05 |
| Secante modificada | 268.328157 | 3 | 0.0004 | 1.506042e-02 |

Raíz de referencia (SciPy):

### Análisis

¿Qué método necesitó menos iteraciones y cuál más? Newton y secante, biseccion y falsa posoción
¿Por qué los cinco no dan
exactamente el mismo número? Por diferencias en el metodo utilizado y sus calculos 
¿Alguno no alcanzó la tolerancia o tardó mucho más que
los otros? ¿Por qué? no

## 5. Cada integrante en su computadora

Cada integrante corre `raices.c` con la ecuación del equipo en su propia computadora y sube
su captura con un commit propio (ver `COMO_CORRER.md`, sección 7).

| Integrante | Usuario de GitHub | Captura |
|---|---|---|
| | | `img/07-integrante-apellido.png` |
| | | |
| | | |

![Integrante 1](img/07-integrante-apellido.png)

## Uso de inteligencia artificial

Ninguno / Cuál y para qué.
si deepseek para hacer la grafica
## Referencias
[1] Chapra, S. C., & Canale, R. P. (2015). Métodos Numéricos para Ingenieros (7a ed.). McGraw-Hill. Capítulos 5
y 6.
[2] Burden, R. L., & Faires, J. D. (2011). Análisis Numérico (9a ed.). Cengage Learning. Capítulo 2.

## 1151039 Métodos Numéricos CTG06
## trimestre 26O  licenciatura en ingieneria civil 
## Cazares Gonzalez Kevin Uriel  Profesor:GABRIEL HURTADO AVILES   06/10/2026

### Este documento resume los conceptos fundamentales de los métodos numéricos, su aplicación en ingeniería civil, las herramientas disponibles y el entorno de trabajo del curso. Está basado principalmente en Chapra, S. C., & Canale, R. P. (2015). Métodos Numéricos para Ingenieros (7a ed.). McGraw-Hill.
Tabla de contenidos

  -  ¿Qué son los métodos numéricos?

  -  Aplicación en Ingeniería Civil

  -  Herramientas para trabajar con métodos numéricos

  -  Herramientas del curso

  -  Referencias

### ¿Qué son los métodos numéricos?

Los métodos numéricos son técnicas mediante las cuales se formulan problemas matemáticos de manera que puedan resolverse con operaciones aritméticas básicas (suma, resta, multiplicación, división). En esencia, transforman un problema continuo en un problema discreto que una computadora puede resolver paso a paso.
Diferencia con la solución analítica

Una solución analítica se obtiene mediante manipulación algebraica y cálculo, expresándose como una fórmula cerrada que permite calcular el valor de la variable dependiente para cualquier valor de la variable independiente. Por ejemplo, para x² = 5, la solución analítica es x = √5.

En contraste, el método numérico entrega valores discretos (una aproximación numérica, como x ≈ 2.236) que solo son válidos en puntos específicos y no constituyen una función continua.
¿Por qué el resultado es aproximado?

Los métodos numéricos introducen dos tipos fundamentales de error:

- Errores de truncamiento: Ocurren porque el método reemplaza un problema matemático exacto (por ejemplo, una derivada) por una aproximación (como una serie de Taylor truncada o una diferencia finita). Este error es inherente al método.

- Errores de redondeo: Surgen porque la computadora almacena números con un número finito de dígitos. Los números reales se redondean o truncan al representarse en memoria.

Papel del error

El error no es un defecto que invalide el método, sino una medida de calidad. En ingeniería, el objetivo no es eliminar el error (lo cual es imposible en aritmética finita), sino controlarlo y asegurar que esté por debajo de una tolerancia predefinida. 

### Aplicación en Ingeniería Civil

En ingeniería civil, los métodos numéricos son indispensables porque la mayoría de los problemas reales involucran geometrías irregulares, propiedades variables en el espacio y condiciones de frontera complejas que no tienen solución analítica cerrada.
Problema concreto: Análisis de estabilidad de columnas con rigidez variable

En el estudio de pandeo de una columna, si la rigidez a flexión EI es constante, existe una fórmula analítica (carga crítica de Euler: P_E = π²EI / L²). Pero si la columna es a husada o tiene refuerzos locales, la rigidez varía con la altura I(x), y no existe solución de forma cerrada. Se debe discretizar la columna en elementos finitos (o diferencias finitas), construir una matriz de rigidez y resolver un problema de valores propios numéricamente para obtener la carga crítica.
Problema concreto 2: Asentamiento de terraplenes sobre suelos blandos

### Herramientas para trabajar con métodos numéricos

Panorama por familias:

|Familia	|Ejemplos	|Fortaleza principal
|---|---|---|
|Lenguajes compilados	|C, C++, Fortran	|Máximo rendimiento y control de memoria|
|Lenguajes interpretados	|Python, R	|Productividad del programador|
|Entornos matriciales	|MATLAB, GNU Octave	|Manejo nativo de matrices y vectores|
|Python científico	|NumPy, SciPy, Matplotlib	|Ecosistema completo para cálculo y visualización|
|Álgebra simbólica	|SymPy, Mathematica	|Manipulación exacta de expresiones|
|Bibliotecas de base	|BLAS, LAPACK	|Operaciones matriciales de alto rendimiento|

   
    Sobre el libro de Chapra y Canale (2015): Esta séptima edición utiliza MATLAB como entorno principal de cómputo. Todos los algoritmos se presentan como archivos-M de MATLAB, y los apéndices incluyen funciones integradas de MATLAB. También menciona Excel y MathCAD como herramientas complementarias para algunos ejemplos.

### Herramientas del curso

Las versiones exactas de cada herramienta se obtienen ejecutando los comandos correspondientes dentro del contenedor Docker.
Docker

Docker es una plataforma de contenedores que empaqueta una aplicación con todas sus dependencias (bibliotecas, intérpretes, compiladores) en una imagen aislada. Al ejecutar esa imagen se crea un contenedor: un proceso aislado que comparte el kernel del sistema operativo anfitrión pero tiene su propio sistema de archivos y entorno. Esto garantiza que el software funcione de manera idéntica en cualquier máquina.
Docker frente a una máquina virtual

Una máquina virtual (VM) emula hardware completo y ejecuta un sistema operativo invitado completo sobre un hipervisor. Un contenedor Docker no emula hardware ni ejecuta un SO completo: comparte el kernel del anfitrión y solo aísla el espacio de usuario. Como consecuencia, los contenedores son mucho más ligeros (megabytes frente a gigabytes), arrancan en segundos y tienen menor sobrecarga de recursos. La VM ofrece aislamiento más fuerte; el contenedor ofrece portabilidad y eficiencia.
Dockerfile, compose.yaml y comandos

  
Comandos esenciales:

| Comando | Descripción |
| :--- | :--- |
| docker compose up -d | Construye (si es necesario), crea e inicia los contenedores en segundo plano (detached). |
| docker compose exec <servicio> <comando> | Ejecuta un comando dentro de un contenedor que ya está corriendo (por ejemplo, abrir una shell). |
| docker compose stop | Detiene los contenedores sin eliminarlos. Los datos en volúmenes persisten. |
| docker compose down | Detiene y elimina los contenedores, redes y (opcionalmente) volúmenes. |
| docker compose ps | Lista el estado de los contenedores del proyecto. |
| docker compose logs | Muestra los registros de salida de los contenedores. |


    Diferencia entre apagar y borrar: stop apaga el contenedor pero conserva su sistema de archivos y metadatos. down elimina el contenedor por completo. Es análogo a apagar un computador versus formatearlo.

### GNU Octave

Es un entorno de programación para cálculo numérico, compatible en gran medida con la sintaxis de MATLAB. Ofrece operaciones matriciales nativas, funciones para resolución de sistemas lineales, integración, ecuaciones diferenciales y visualización. Se usa en el curso como alternativa libre a MATLAB, siguiendo la línea de los entornos matriciales descritos por Chapra.

### Python

Lenguaje de programación interpretado, de propósito general, con un ecosistema científico maduro. En el contexto de métodos numéricos se emplean NumPy (arreglos y operaciones vectorizadas), SciPy (algoritmos numéricos) y Matplotlib (gráficas). Su ventaja es la versatilidad: un mismo lenguaje sirve para prototipado, análisis de datos, automatización y visualización.

### C con gcc

C es un lenguaje compilado de alto rendimiento. gcc (GNU Compiler Collection) es el compilador. Se usa en el curso para implementar algoritmos numéricos desde cero, comprendiendo la gestión de memoria, los tipos de datos de precisión (float, double) y el impacto del redondeo en el rendimiento y la exactitud. Escribir un método numérico en C obliga a enfrentar los detalles de bajo nivel que los entornos matriciales ocultan.
Verificación de versiones

Para obtener las versiones exactas dentro del contenedor:
bash

- `docker compose exec <servicio> octave --version`
- `docker compose exec <servicio> python3 --version`
- `docker compose exec <servicio> gcc --version`
- `docker compose exec <servicio> python3 -c `
- `docker compose exec <servicio> python3 -c `
- `docker compose exec <servicio> python3 -c `

##Referencias

    Chapra, S. C., & Canale, R. P. (2015). Métodos Numéricos para Ingenieros (7a ed.). McGraw-Hill.

    Documentación oficial de Docker: https://docs.docker.com/

    Documentación oficial de GNU Octave: https://octave.org/

    Documentación oficial de NumPy, SciPy y Matplotlib: https://numpy.org/, https://scipy.org/, https://matplotlib.org/
    
### docker compose up -d --build terminado

<img width="1422" height="649" alt="Captura de pantalla 2026-10-05 203727" src="https://github.com/user-attachments/assets/a538eff2-b831-4c0e-8cb8-35b942522286" />

### docker compose ps con la columna STATUS en «Up».

<img width="1439" height="358" alt="Captura de pantalla 2026-10-05 203825" src="https://github.com/user-attachments/assets/fdc87e28-c744-44dc-a336-9b6f426c95fc" />

### Dentro del contenedor: octave --version, python3 --version y gcc --version. 

<img width="1417" height="701" alt="Captura de pantalla 2026-10-05 204952" src="https://github.com/user-attachments/assets/d2822b71-9480-409b-8a6a-dcc0fea248df" />

### Docker Desktop con el contenedor del curso en la lista.
<img width="1107" height="573" alt="Captura de pantalla 2026-10-06 200512" src="https://github.com/user-attachments/assets/a65f4261-b216-4d77-b9e1-21f48c1855a3" />

### Sus dos programas ejecutándose dentro del contenedor.

<img width="1430" height="438" alt="Captura de pantalla 2026-10-05 204605" src="https://github.com/user-attachments/assets/28b0b72f-26cb-4a91-9e92-24d7070627af" />

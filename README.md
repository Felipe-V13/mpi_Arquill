# Proyecto de Compilación y Ejecución en C con MPI y OpenMP

Este proyecto contiene varios programas en lenguaje C que exploran diferentes enfoques de programación paralela, utilizando tecnologías como MPI (Message Passing Interface) y OpenMP, además de una implementación serial. Cada uno de estos programas tiene un propósito específico y demuestra el uso de paradigmas de computación paralela para optimizar el rendimiento en operaciones matemáticas intensivas y procesamiento de imágenes.

## Tabla de Contenidos

- [Prerrequisitos](#prerrequisitos)
- [Programas y su Compilación](#programas-y-su-compilación)
  - [SUM_MPI: Suma Paralela](#sum_mpi-suma-paralela)
  - [MATRICES_MULTIPLICACION: Multiplicación de Matrices](#matrices_multiplicacion-multiplicación-de-matrices)
  - [Sobel](#sobel)
    - [Sobel Serial](#sobel_serial)
    - [Sobel con OpenMP](#sobel_openmp)
    - [Sobel con MPI](#sobel_mpi)
- [Tutorial de Instalación](#tutorial-de-instalación)

## Prerrequisitos

Antes de compilar y ejecutar estos programas, asegúrate de tener las siguientes herramientas instaladas:

1. **MPI (Message Passing Interface):** Se requiere `mpicc`, el compilador MPI. Puedes instalar MPI mediante bibliotecas como [OpenMPI](https://www.open-mpi.org/) o [MPICH](https://www.mpich.org/).
2. **GCC (GNU Compiler Collection):** Para compilar tanto programas seriales como los que usan OpenMP.
3. **Biblioteca Matemática:** La biblioteca matemática `libm` (incluida en la mayoría de distribuciones de Linux) es necesaria para funciones matemáticas avanzadas.

Para verificar si tienes instalados `mpicc` y `gcc`, usa:

```bash
mpicc --version
gcc --version
Programas y su Compilación
SUM_MPI: Suma Paralela
Descripción: Este programa realiza la suma de elementos de un conjunto de datos de forma paralela utilizando MPI, distribuyendo los cálculos entre múltiples procesos.

Archivo Fuente: sum_mpi.c
Compilación:

bash
Copiar código
mpicc sum_mpi.c -o SUM_MPI
Ejecución:

bash
Copiar código
mpirun --hostfile /etc/hosts -np <número_de_procesos> ./SUM_MPI
Nota: Reemplaza <número_de_procesos> con el número de procesos que deseas usar para la ejecución paralela.

MATRICES_MULTIPLICACION: Multiplicación de Matrices
Descripción: Este programa ejecuta la multiplicación de matrices de forma paralela utilizando MPI para dividir la operación entre diferentes procesos, lo que permite manejar matrices grandes con un rendimiento optimizado.

Archivo Fuente: matrices.c
Compilación:

bash
Copiar código
mpicc matrices.c -o MATRICES_MULTIPLICACION
Ejecución:

bash
Copiar código
mpirun --hostfile /etc/hosts -np <número_de_procesos> ./MATRICES_MULTIPLICACION
Nota: Asegúrate de que el archivo /etc/hosts incluya las IP o nombres de los hosts donde se ejecutarán los procesos MPI. Esto facilita la comunicación entre diferentes nodos en un entorno de cómputo distribuido.

Sobel
El filtro Sobel es una técnica de procesamiento de imágenes para la detección de bordes. Se implementa aquí en tres versiones: serial, paralela con OpenMP y paralela con MPI.

Sobel Serial
Descripción: Implementación serial del filtro Sobel, procesando la imagen en un único hilo sin paralelización. Ideal para entender la lógica básica de Sobel.

Archivo Fuente: sobel_serial.c
Compilación:

bash
Copiar código
gcc -o sobel_serial sobel_serial.c -lm
Ejecución:

bash
Copiar código
./sobel_serial
Sobel con OpenMP
Descripción: Implementación del filtro Sobel con OpenMP, que permite distribuir la carga de procesamiento en múltiples hilos dentro de un solo equipo, mejorando el rendimiento en sistemas multicore.

Archivo Fuente: sobel_openmp.c
Compilación:

bash
Copiar código
gcc -o SOBEL_OPENMP sobel_openmp.c -lm -fopenmp
Ejecución:

bash
Copiar código
./SOBEL_OPENMP
Nota: Asegúrate de que tu sistema soporta OpenMP y está configurado para usar múltiples núcleos.

Sobel con MPI
Descripción: Implementación del filtro Sobel utilizando MPI para ejecutar en múltiples procesos, permitiendo el procesamiento distribuido en varios nodos de un clúster.

Archivo Fuente: sobel_mpi.c
Compilación:

bash
Copiar código
mpicc -o SOBEL_MPI sobel_mpi.c -lm
Ejecución:

bash
Copiar código
mpirun --hostfile /etc/hosts -np <número_de_procesos> ./SOBEL_MPI
Nota: Como con otros programas MPI, verifica que el archivo /etc/hosts esté configurado correctamente.

Tutorial de Instalación
Para una guía detallada sobre cómo instalar y configurar MPI, OpenMP y las herramientas de compilación necesarias, consulta este playlist en YouTube, donde encontrarás tutoriales paso a paso sobre:

Instalación y configuración de OpenMPI y MPICH en Linux.
Uso básico de MPI y OpenMP en C.
Ejecución de programas MPI en un entorno distribuido.
Este tutorial es ideal para principiantes y proporciona un soporte visual para configurar y ejecutar aplicaciones de cómputo paralelo.

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

# Reporte de práctica: Elementos fundamentales de los lenguajes de programación

**Alumno:** Isarel Gomez Ahumada

**Materia:** Paradigmas de la programacion

**Profesor:** Carlos Gallegos

**Fecha:** 26/09/25  

---

## Introducción

El objetivo de esta práctica es **identificar los elementos fundamentales de los lenguajes de programación** en los archivos `biblioteca.c` y `memory_management.c`, analizando cómo se implementan conceptos como nombres, marcos de activación, bloques de alcance, administración de memoria, expresiones, comandos, control de secuencia, subprogramas y tipos de datos.

Repositorio:
[https://github.com/gallegosj89/portafolio](https://github.com/gallegosj89/portafolio)

## Desarrollo

### 1. Nombres (Identificadores)

En C, los **nombres** son identificadores que representan variables, funciones, estructuras o constantes.  
Ejemplo del archivo `biblioteca.c`:

```c
struct Libro {
    char titulo[50];
    char autor[50];
    int anio;
};

Libro, titulo, autor, anio → son nombres que identifican la estructura y sus atributos.

También aparecen nombres como agregarLibro, mostrarLibros, main.

Estos nombres permiten referirnos a datos y funciones a lo largo del programa.
```

### 2. Marcos de activación (Stack Frames)

Cada vez que se ejecuta una función, se crea un marco de activación en la pila que contiene sus variables locales y parámetros.

***Ejemplo:***

```c
void agregarLibro(struct Libro *lista, int *contador) {
    struct Libro nuevo;
    printf("Ingrese titulo: ");
    scanf("%s", nuevo.titulo);
    lista[*contador] = nuevo;
    (*contador)++;
}
Cuando se llama a agregarLibro():

Se reserva espacio en la pila para la variable local nuevo.

Al terminar, el marco se destruye y la pila regresa a su estado anterior.
```

### 3. Bloques de alcance

En C existen variables globales y locales:

```c
struct Libro listaLibros[100]; // Variable global
int contador = 0;              // Visible en todo el archivo

void mostrarLibros() {
    for (int i = 0; i < contador; i++) {  // Variable local i
        printf("%s\n", listaLibros[i].titulo);
    }
}
listaLibros y contador → Alcance global.

i → Alcance local a la función mostrarLibros().
```

### 4. Administración de memoria

En memory_management.c se ejemplifica la reserva y liberación dinámica de memoria:

```c
int *arr = (int*) malloc(5 * sizeof(int));
if (arr == NULL) {
    printf("Error al asignar memoria\n");
}
for (int i = 0; i < 5; i++) {
    arr[i] = i + 1;
}
free(arr);
malloc → reserva memoria en el heap.

free → libera la memoria usada.
```

**Esto es importante para evitar fugas de memoria.**

### 5. Expresiones

Son combinaciones de valores, variables y operadores.

```c
Ejemplo:
arr[i] = i + 1;          // Expresión aritmética
if (anio > 2000) { ... } // Expresión booleana
i + 1 es una expresión aritmética.

anio > 2000 es una expresión lógica usada en una condición.
```

## 6. Comandos (Sentencias)

Los comandos son instrucciones que ejecuta el programa:

```c
printf("Ingrese titulo: ");   // Comando de salida
scanf("%s", nuevo.titulo);   // Comando de entrada
return 0;                    // Comando de terminación
Cada línea de código cambia el estado del programa o ejecuta una acción.
```

### 7. Control de secuencia

Selección
Uso de if y switch para tomar decisiones:

c
Copiar código
if (anio > 2000) {
    printf("Libro moderno\n");
} else {
    printf("Libro antiguo\n");
}
Iteración
Uso de ciclos for y while:

c
Copiar código
for (int i = 0; i < contador; i++) {
    printf("%s\n", listaLibros[i].titulo);
}
Recursión
En caso de no existir en estos archivos, podemos mencionar:

Este código no presenta funciones recursivas, pero el concepto se refiere a que una función se llame a sí misma para resolver un problema, como el cálculo de factorial.

## 8. Subprogramas (Funciones)

En C, las funciones permiten modularizar el código.

Ejemplo de biblioteca.c:

c
Copiar código
void mostrarLibros() {
    for (int i = 0; i < contador; i++) {
        printf("%s\n", listaLibros[i].titulo);
    }
}
Aquí mostrarLibros() es un subprograma que imprime la lista de libros.

## 9. Tipos de datos

Se usan tanto primitivos como compuestos:

Primitivos:

int, char, float

Compuestos:

```c
struct Libro
Copiar código
struct Libro {
    char titulo[50];
    char autor[50];
    int anio;
};
```

# PA2 - Computación Gráfica

## Celda Industrial Robotizada 3D

Proyecto desarrollado en **C++ utilizando OpenGL y FreeGLUT** para el curso de **Computación Gráfica**.

El proyecto representa una **celda industrial robotizada en un entorno tridimensional**, donde se aplican conceptos de modelamiento 3D, transformaciones geométricas, modelado jerárquico, curvas paramétricas, superficies y manejo de cámara.

---

## Descripción

La escena está compuesta por diferentes objetos que representan un entorno industrial.

El elemento principal es un **brazo robótico articulado**, cuyos movimientos pueden ser controlados mediante el teclado.

La escena incluye:

- Brazo robótico articulado.
- Base del robot.
- Hombro.
- Brazo.
- Codo.
- Antebrazo.
- Muñeca.
- Pinza.
- Cinta transportadora.
- Cajas.
- Mesa de trabajo.
- Panel de control.
- Lámpara industrial.
- Barrera de seguridad.
- Sensor.
- Piso industrial.
- Curva paramétrica Bézier.
- Superficie paramétrica en modo wireframe.

---

## Tecnologías utilizadas

- C++
- OpenGL
- FreeGLUT
- GLU
- CMake
- CLion / compilador compatible con C++17

---

## Conceptos aplicados

Durante el desarrollo del proyecto se aplicaron los siguientes conceptos de Computación Gráfica:

### Transformaciones geométricas

Se utilizaron las principales transformaciones de OpenGL:

```cpp
glTranslatef();
glRotatef();
glScalef();
```

Estas permiten realizar:

- Traslación.
- Rotación.
- Escalamiento.

---

## Modelado jerárquico

El brazo robótico utiliza una estructura jerárquica.

La transformación de una articulación afecta a las partes que dependen de ella.

La jerarquía principal es:

```text
Base
 └── Hombro
      └── Brazo
           └── Codo
                └── Antebrazo
                     └── Muñeca
                          └── Pinza
```

Para controlar las transformaciones locales de cada elemento se utilizan:

```cpp
glPushMatrix();
glPopMatrix();
```

---

## Curva paramétrica

El proyecto incluye una **curva Bézier cúbica** utilizada para representar un cable dentro de la escena.

La curva se calcula mediante cuatro puntos de control utilizando la ecuación:

```text
B(t) = (1-t)³P0
     + 3(1-t)²tP1
     + 3(1-t)t²P2
     + t³P3
```

donde:

```text
0 <= t <= 1
```

---

## Superficie paramétrica

También se implementó una superficie generada matemáticamente y representada mediante una malla **wireframe**.

La superficie utiliza los parámetros `u` y `v` para generar los diferentes puntos de la malla tridimensional.

Esto permite visualizar cómo una superficie puede construirse mediante ecuaciones paramétricas.

---

## Cámaras

El proyecto cuenta con diferentes vistas para observar el escenario.

| Tecla | Vista |
|---|---|
| F1 | Perspectiva |
| F2 | Frontal |
| F3 | Lateral |
| F4 | Superior |

También se puede mover la cámara utilizando las flechas del teclado.

---

## Controles

### Brazo robótico

| Tecla | Acción |
|---|---|
| 1 / 2 | Rotar base |
| 3 / 4 | Rotar hombro |
| 5 / 6 | Rotar codo |
| 7 / 8 | Rotar muñeca |
| 9 / 0 | Abrir / cerrar pinza |

### Transformaciones

| Tecla | Acción |
|---|---|
| J / L | Trasladar caja |
| Z / X | Reducir / aumentar escala del robot |
| A | Activar o detener cinta transportadora |

### Cámara

| Tecla | Acción |
|---|---|
| F1 | Vista perspectiva |
| F2 | Vista frontal |
| F3 | Vista lateral |
| F4 | Vista superior |
| Flechas | Orbitar cámara |
| + / - | Acercar / alejar cámara |

### Otros controles

| Tecla | Acción |
|---|---|
| W | Activar/desactivar wireframe |
| R | Reiniciar escena |
| ESC | Cerrar aplicación |

---

## Estructura del proyecto

```text
PA2-Computacion-Grafica/
│
├── main.cpp
├── CMakeLists.txt
└── README.md
```

---

## Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/TU-USUARIO/PA2-Computacion-Grafica.git
```

Ingresar a la carpeta:

```bash
cd PA2-Computacion-Grafica
```

---

## Compilación

El proyecto utiliza **CMake**.

Crear una carpeta de compilación:

```bash
mkdir build
cd build
```

Generar los archivos de compilación:

```bash
cmake ..
```

Compilar:

```bash
cmake --build .
```

FreeGLUT se descarga automáticamente mediante `FetchContent` definido en el archivo `CMakeLists.txt`.

---

## Requisitos

Para ejecutar el proyecto se recomienda contar con:

- Windows 10/11.
- CMake 3.20 o superior.
- Compilador compatible con C++17.
- OpenGL.
- Git.
- CLion, Visual Studio o IDE compatible con CMake.

---

## Objetivo del proyecto

El objetivo principal es aplicar los conceptos fundamentales del modelamiento tridimensional utilizando OpenGL.

Entre ellos:

- Construcción de objetos 3D.
- Uso de primitivas geométricas.
- Transformaciones.
- Sistemas de coordenadas.
- Modelado jerárquico.
- Manipulación interactiva.
- Curvas paramétricas.
- Superficies paramétricas.
- Representación wireframe.
- Manejo de diferentes vistas de cámara.

---

## Resultado

El resultado es una escena tridimensional interactiva que representa una **celda industrial robotizada**, permitiendo modificar las articulaciones del robot, mover objetos y observar el escenario desde diferentes perspectivas.

---

## Autor

**Meza Pastrana, Diego Armando 
Meza Pastrana, Diego Armando **

Curso: **Computación Gráfica**

Proyecto: **PA2 - Modelamiento 3D**

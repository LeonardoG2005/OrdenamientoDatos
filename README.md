# Visualizador y Comparador de Algoritmos de Ordenamiento

## 📋 Propósito del Proyecto

Este proyecto es una aplicación web interactiva desarrollada para la materia **Análisis y Diseño de Algoritmos**. Su objetivo principal es demostrar el funcionamiento de diferentes algoritmos de ordenamiento aplicados a datos reales obtenidos de una API del gobierno colombiano.

La aplicación permite visualizar de manera práctica cómo distintos algoritmos de ordenamiento procesan información agrícola (producción, áreas de cultivo, etc.), facilitando la comprensión de sus características, ventajas y limitaciones según el tipo de datos que manejan.

## 🎯 ¿Qué Problema Resuelve?

El proyecto aborda varios conceptos fundamentales del análisis de algoritmos:

- **Comparación práctica de algoritmos**: Permite experimentar con 9 algoritmos de ordenamiento diferentes sobre el mismo conjunto de datos
- **Restricciones de algoritmos**: Demuestra que no todos los algoritmos funcionan con todos los tipos de datos (negativos, flotantes, cadenas de texto)
- **Visualización de resultados**: Muestra cómo los datos se reorganizan después de aplicar cada algoritmo
- **Aplicación real**: Utiliza datos reales de producción agrícola, demostrando que los algoritmos no son solo conceptos teóricos

## 🚀 Cómo Funciona la Aplicación

### Flujo General

1. **Carga de datos**: Al abrir la aplicación, se obtienen automáticamente datos de producción agrícola desde la API del gobierno colombiano (`datos.gov.co`)
2. **Modificación de datos**: Los años se modifican aleatoriamente (incluyendo valores negativos) para demostrar las limitaciones de ciertos algoritmos
3. **Visualización paginada**: Los datos se muestran en una tabla con paginación (20 registros por página)
4. **Selección de ordenamiento**: El usuario selecciona una columna y un algoritmo de ordenamiento
5. **Validación inteligente**: La aplicación deshabilita automáticamente los algoritmos que no funcionan con el tipo de dato seleccionado
6. **Ordenamiento**: Los datos se reorganizan según el algoritmo elegido
7. **Inversión**: Opcionalmente, se puede invertir el orden de la tabla

### Organización Interna

- **`api.js`**: Controla la obtención, paginación y lógica principal de ordenamiento
- **Archivos de algoritmos**: Cada algoritmo está en su propio archivo para facilitar el mantenimiento
- **Validación dinámica**: Antes de permitir el ordenamiento, se verifican las características de los datos (negativos, flotantes, strings)
- **Interfaz modal**: Bootstrap proporciona una interfaz limpia para seleccionar opciones de ordenamiento

## 🧮 Algoritmos Utilizados

### 1. **Bubble Sort** (`bubblesort.js`)
- **Descripción**: Compara pares de elementos adyacentes y los intercambia si están en el orden incorrecto
- **Por qué se usa**: Es el algoritmo más simple, ideal para enseñar el concepto de ordenamiento
- **Complejidad**: O(n²) en el peor caso
- **Funciona con**: Números (positivos, negativos, flotantes) y cadenas de texto

### 2. **Quick Sort** (`quick.js`)
- **Descripción**: Divide el arreglo usando un pivote y ordena recursivamente las particiones
- **Por qué se usa**: Muy eficiente en la práctica, uno de los más rápidos en promedio
- **Complejidad**: O(n log n) en promedio, O(n²) en el peor caso
- **Funciona con**: Números y cadenas de texto

### 3. **Merge Sort** (`mergeSort.js`)
- **Descripción**: Divide el arreglo en mitades, las ordena y luego las combina
- **Por qué se usa**: Garantiza rendimiento consistente, es estable
- **Complejidad**: O(n log n) siempre
- **Funciona con**: Números y cadenas de texto

### 4. **Heap Sort** (`heapSort.js`)
- **Descripción**: Construye un heap (montículo) y extrae elementos ordenados
- **Por qué se usa**: Eficiente en espacio, no necesita memoria adicional
- **Complejidad**: O(n log n) siempre
- **Funciona con**: Números y cadenas de texto

### 5. **Insertion Sort** (`insertionSort.js`)
- **Descripción**: Construye el arreglo ordenado insertando elementos uno por uno
- **Por qué se usa**: Muy eficiente para arreglos pequeños o casi ordenados
- **Complejidad**: O(n²) en el peor caso, O(n) en el mejor
- **Funciona con**: Números y cadenas de texto

### 6. **Selection Sort** (`selectionSort.js`)
- **Descripción**: Busca el elemento mínimo y lo coloca en su posición correcta
- **Por qué se usa**: Simple de entender, útil para conjuntos pequeños
- **Complejidad**: O(n²) siempre
- **Funciona con**: Números y cadenas de texto

### 7. **Counting Sort** (`countingSort.js`)
- **Descripción**: Cuenta las ocurrencias de cada valor y reconstruye el arreglo ordenado
- **Por qué se usa**: Extremadamente rápido para rangos limitados de números enteros
- **Complejidad**: O(n + k) donde k es el rango de valores
- **Limitaciones**: ⚠️ Solo funciona con números enteros positivos

### 8. **Radix Sort** (`radixSort.js`)
- **Descripción**: Ordena dígito por dígito usando Counting Sort como subrutina
- **Por qué se usa**: Muy eficiente para números enteros con muchos dígitos
- **Complejidad**: O(d × n) donde d es el número de dígitos
- **Limitaciones**: ⚠️ Solo funciona con números enteros positivos

### 9. **Bucket Sort** (`bucketSort.js`)
- **Descripción**: Distribuye elementos en "cubetas" y ordena cada cubeta
- **Por qué se usa**: Eficiente cuando los datos están uniformemente distribuidos
- **Complejidad**: O(n + k) en promedio
- **Limitaciones**: ⚠️ Solo funciona con números positivos

## 💻 Tecnologías y Herramientas Usadas

- **HTML5**: Estructura de la página web
- **CSS3**: Estilos personalizados (`style.css`)
- **JavaScript (ES6+)**: Lógica de la aplicación y todos los algoritmos
- **Bootstrap 5**: Framework CSS para interfaz responsive y componentes (modal, tabla, botones)
- **jQuery 3.6**: Manipulación del DOM y manejo de eventos
- **Fetch API**: Obtención de datos desde la API del gobierno
- **API de Datos Abiertos de Colombia**: Fuente de datos reales sobre producción agrícola

## 📁 Estructura del Proyecto

```
FinalAlgoritmos/
│
├── index.html              # Página principal con la tabla y modal de ordenamiento
│
├── css/
│   └── style.css          # Estilos personalizados (fondo, tabla, botones)
│
└── js/
    ├── api.js             # Lógica principal: carga de datos, paginación y validación
    ├── buttons.js         # Funcionalidad de botones (no utilizada actualmente)
    ├── invert.js          # Función para invertir el orden de la tabla
    │
    ├── bubblesort.js      # Algoritmo Bubble Sort
    ├── quick.js           # Algoritmo Quick Sort
    ├── mergeSort.js       # Algoritmo Merge Sort
    ├── heapSort.js        # Algoritmo Heap Sort
    ├── insertionSort.js   # Algoritmo Insertion Sort
    ├── selectionSort.js   # Algoritmo Selection Sort
    ├── countingSort.js    # Algoritmo Counting Sort (solo enteros positivos)
    ├── radixSort.js       # Algoritmo Radix Sort (solo enteros positivos)
    └── bucketSort.js      # Algoritmo Bucket Sort (solo positivos)
```

### Descripción de Archivos Clave

- **`index.html`**: Contiene la interfaz completa con tabla de datos, botones de acción y modal de configuración
- **`api.js`**: Archivo central que maneja la API, genera datos aleatorios (incluyendo años negativos), implementa la paginación y valida qué algoritmos están disponibles según el tipo de datos
- **`style.css`**: Define el esquema de colores (fondo azul, encabezados morados) y estilos de interacción
- **Archivos de algoritmos**: Cada algoritmo está modularizado en su propio archivo para facilitar el estudio individual

## 🔧 Instrucciones para Ejecutar el Proyecto

### Requisitos Previos
- Un navegador web moderno (Chrome, Firefox, Edge, Safari)
- Conexión a Internet (para cargar Bootstrap, jQuery y la API de datos)

### Pasos para Ejecutar

1. **Descargar o clonar el proyecto**
   ```bash
   git clone https://github.com/LeonardoG2005/OrdenamientoDatos.git
   ```

2. **Navegar a la carpeta del proyecto**
   ```bash
   cd FinalAlgoritmos
   ```

3. **Abrir el archivo HTML**
   - Opción 1: Hacer doble clic en `index.html`
   - Opción 2: Usar un servidor local (recomendado):
     ```bash
     # Con Python 3
     python -m http.server 8000
     
     # Con Node.js (si tienes http-server instalado)
     npx http-server
     ```
   - Luego abrir `http://localhost:8000` en el navegador

4. **Usar la aplicación**
   - Los datos se cargarán automáticamente
   - Haz clic en "Ordenar" para elegir una columna y algoritmo
   - La aplicación te indicará si algún algoritmo no es compatible con los datos seleccionados
   - Haz clic en "Invertir" para revertir el orden actual

### Características Especiales

- **Validación inteligente**: Si seleccionas una columna con números negativos o flotantes, los algoritmos Counting, Radix y Bucket se deshabilitarán automáticamente con una explicación
- **Datos modificados**: Los años se generan aleatoriamente (incluyendo valores negativos entre -1000 y 990) para demostrar las limitaciones de ciertos algoritmos

## 🎓 Conclusión

Este proyecto es una herramienta educativa valiosa para el curso de **Análisis y Diseño de Algoritmos** porque:

1. **Demuestra conceptos teóricos en práctica**: Ver cómo funcionan los algoritmos con datos reales facilita la comprensión
2. **Enseña restricciones de algoritmos**: No todos los algoritmos son universales; algunos tienen limitaciones según el tipo de datos
3. **Permite experimentación**: Los estudiantes pueden probar diferentes algoritmos sobre las mismas columnas y comparar resultados
4. **Muestra la importancia de la validación**: La aplicación valida automáticamente qué algoritmos son aplicables
5. **Integra conocimientos**: Combina estructuras de datos, análisis de complejidad, y desarrollo web
6. **Usa datos reales**: Trabajar con información del gobierno colombiano hace el ejercicio más relevante que usar datos ficticios

El proyecto sirve como referencia práctica para comprender que la elección del algoritmo correcto depende no solo de la eficiencia, sino también de las características específicas de los datos que se van a procesar.

---

**Autor**: Leonardo Guevara 
**Repositorio**: [https://github.com/LeonardoG2005/OrdenamientoDatos](https://github.com/LeonardoG2005/OrdenamientoDatos)  
**Materia**: Análisis y Diseño de Algoritmos

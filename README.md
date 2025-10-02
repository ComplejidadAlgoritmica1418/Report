# Sistema de Búsqueda de Rutas Tipo Waze: Análisis de Complejidad Algorítmica

**Nombre de los integrantes**:  
- Sebastián Eduardo Hernández Poma  
- [Nombre del segundo integrante]  
- [Nombre del tercer integrante]  

**Fecha de entrega**: [Fecha]  

**Código de la materia**: **CC184 - Complejidad Algorítmica**

---

## Índice
1. [Introducción](#introducción)  
2. [Descripción del problema](#descripción-del-problema)  
3. [Descripción del conjunto de datos](#descripción-del-conjunto-de-datos)  
4. [Propuesta preliminar](#propuesta-preliminar)  
5. [Diseño del aplicativo](#diseño-del-aplicativo)  
6. [Validación de resultados y pruebas](#validación-de-resultados-y-pruebas)  
7. [Conclusiones](#conclusiones)  
8. [Referencias bibliográficas](#referencias-bibliográficas)  

---

## Introducción
El objetivo de este trabajo es aplicar técnicas de **complejidad algorítmica** para resolver el problema de encontrar la ruta más corta entre dos puntos en una ciudad. Para ello, modelamos la ciudad como un **grafo** donde las intersecciones de las calles son los **nodos** y las calles son las **aristas**. Utilizando algoritmos de búsqueda de rutas en grafos, como **Dijkstra**, buscamos optimizar el tiempo de recorrido, considerando el **tráfico** y la **hora del día** como factores dinámicos en las aristas del grafo.

Este tipo de problema tiene una gran aplicación práctica, ya que puede ser utilizado para **optimizar rutas en aplicaciones como Waze**, lo que facilita la movilidad urbana y mejora la eficiencia del transporte.

---

## Descripción del problema
El problema consiste en encontrar la **ruta más corta** entre dos puntos en una ciudad representada como un grafo. Los puntos de la ciudad están conectados por calles, y cada calle tiene un peso asociado, que depende de su **longitud** (calculada en base a la latitud y longitud) y de un **factor de tráfico**. Este factor de tráfico varía dependiendo de la **hora del día**, lo que hace que las aristas no sean estáticas sino dinámicas.

### Definición del problema:
- **Entrada**: Dos puntos (intersecciones) en la ciudad.
- **Salida**: La ruta más corta entre esos dos puntos, considerando los tiempos de viaje calculados a partir de la longitud y el tráfico.

### Objetivos:
- Implementar un sistema que calcule la **ruta más corta** entre dos puntos.
- Tener en cuenta la **variabilidad del tráfico** en función de la hora.
- Modelar la ciudad como un grafo, con las intersecciones como nodos y las calles como aristas.

---

## Descripción del conjunto de datos
Para representar la ciudad como un grafo, se utilizarán **datos reales o generados** que incluyan lo siguiente:
- **Intersecciones**: Serán los nodos del grafo.
- **Calles**: Serán las aristas entre los nodos.
- **Latitud y longitud**: Las coordenadas geográficas de cada intersección, necesarias para calcular la longitud de las calles.
- **Peso de las aristas**: Dependiendo de la **longitud** (calculada en base a las coordenadas geográficas) y un **factor de tráfico**, que varía según la hora del día.

### Características del dataset:
- **Número mínimo de nodos**: 1500 (500 por cada integrante del grupo).
- **Representación gráfica**: El grafo será visualizado usando herramientas como **NetworkX** en Python, con la capacidad de mostrar tanto el grafo completo como subgrafos.
- **Datos de tráfico**: Los datos de tráfico se podrán ajustar mediante un valor dinámico que será modificado dependiendo de la hora del día.

### Origen del dataset:
Se utilizarán **datos generados aleatoriamente** para las intersecciones y calles, asegurándose de que la distribución de nodos y aristas sea representativa de una ciudad promedio. También se incorporarán **factores de tráfico simulados**.

---

## Propuesta preliminar
### Técnica y metodología a utilizar:
La **técnica de búsqueda** que utilizaremos es el **algoritmo de Dijkstra**, que es adecuado para encontrar la ruta más corta en un grafo ponderado. Este algoritmo es ampliamente utilizado debido a su eficiencia y precisión, especialmente en grafos donde las aristas tienen pesos variables, como en este caso, que dependen de la longitud y el tráfico.

### Justificación de la elección:
- **Dijkstra** es un algoritmo de **búsqueda en grafos** que encuentra el camino más corto desde un nodo fuente a todos los demás nodos en el grafo, siendo eficiente para este tipo de problemas donde el grafo es denso y las aristas tienen pesos variables.
- **Alternativas**: Se evaluó el uso de otros algoritmos como **A* search**, pero Dijkstra es más adecuado para este tipo de problemas, donde no se tienen objetivos heurísticos claros, sino simplemente la optimización del tiempo de viaje.

### Metodología:
1. **Construcción del grafo**: Se modela la ciudad con nodos (intersecciones) y aristas (calles) con pesos dinámicos basados en la latitud, longitud y tráfico.
2. **Algoritmo de búsqueda**: Se implementa el algoritmo **Dijkstra** para encontrar la ruta más corta entre los dos puntos de entrada.

---

## Diseño del aplicativo
El **diseño del aplicativo** se realizará en Python, utilizando bibliotecas como **NetworkX** para representar el grafo y **Matplotlib** para la visualización. La aplicación recibirá dos intersecciones como entrada y devolverá la ruta más corta considerando el tráfico.

### Componentes clave:
- **Grafo de la ciudad**: Se construirá un grafo donde los nodos representen intersecciones y las aristas las calles.
- **Interfaz gráfica**: Usaremos **Tkinter** o **PyQt** para la interfaz de usuario, donde el usuario podrá ingresar las intersecciones y ver la ruta más corta visualmente.

---

## Validación de resultados y pruebas
### Entradas:
- **Intersección de inicio**: Coordenadas geográficas de la intersección de inicio.
- **Intersección de destino**: Coordenadas geográficas de la intersección de destino.

### Salidas:
- La **ruta más corta** entre los dos puntos, con la duración estimada considerando el tráfico en tiempo real.

### Pruebas realizadas:
- **Prueba de exactitud**: Verificar que el algoritmo devuelve la ruta más corta correctamente mediante comparación con métodos manuales o calculados previamente.
- **Prueba de eficiencia**: Evaluar el tiempo de ejecución para diferentes tamaños del grafo (número de nodos y aristas) y diferentes valores de tráfico.

---

## Conclusiones
Este trabajo presenta una solución eficiente para el cálculo de rutas más cortas en una ciudad utilizando técnicas de complejidad algorítmica. El uso de **Dijkstra** para encontrar la ruta más corta es adecuado para el grafo dinámico que modela las calles y el tráfico. Se puede mejorar el sistema incorporando más **algoritmos de optimización** o implementando un sistema de **actualización en tiempo real del tráfico**.

---

## Referencias bibliográficas
1. Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms* (3rd ed.). MIT Press.
2. "Dijkstra's algorithm", Wikipedia. https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm
3. "A* search algorithm", Wikipedia. https://en.wikipedia.org/wiki/A*_search_algorithm
4. NetworkX documentation. https://networkx.github.io/documentation/stable/

---

Este es el formato HTML que puedes copiar y pegar en tu archivo `.md` de GitHub. Si necesitas realizar algún ajuste o agregar más detalles, ¡avísame!

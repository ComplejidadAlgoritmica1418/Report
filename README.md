# Sistema de Búsqueda de Rutas Tipo Waze: Análisis de Complejidad Algorítmica

**Nombre de los integrantes**:  
- Sebastián Eduardo Hernández Poma  
- Sandra Paula Luyo Correa  
- Luis Piero Rodríguez Rodríguez
- Raúl Bellido Salas

**Fecha de entrega**: 6/10/2025  

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
El objetivo de este trabajo es aplicar técnicas de complejidad algorítmica para resolver el problema de encontrar la ruta más corta entre dos puntos en una ciudad. Para ello, modelamos la ciudad como un grafo donde las intersecciones de las calles son los nodos y las calles son las aristas. Utilizando algoritmos de búsqueda de rutas en grafos, como Dijkstra, buscamos optimizar el tiempo de recorrido, considerando el tráfico y la hora del día como factores dinámicos en las aristas del grafo.

---

<h2>HealthNet – Red de Derivación Médica Inteligente</h2>

<hr>

<h2>1. Planteamiento del problema</h2>
<p>
En distritos urbanos como San Borja (Lima), la saturación hospitalaria y la congestión vial dificultan
la atención médica oportuna. La derivación de pacientes hacia hospitales adecuados requiere no solo 
considerar la distancia geográfica, sino principalmente el <b>tiempo de traslado</b>.
</p>
<p>
El proyecto <b>HealthNet</b> plantea modelar la red vial de la ciudad como un <b>grafo ponderado</b>,
donde los nodos son hospitales, clínicas, pacientes y ambulancias, y las aristas representan las vías,
ponderadas por <i>tiempo estimado de recorrido</i>. 
El objetivo es calcular la <b>ruta más rápida</b> que permita derivar un paciente hacia el hospital adecuado,
aplicando algoritmos de grafos en un entorno simulado.
</p>

<hr>

<h2>2. Fundamentación teórica</h2>
<ul>
  <li><b>Grafos:</b> Representación matemática de la red vial. 
      Cada nodo representa una entidad (hospital, paciente, ambulancia) y cada arista una calle.</li>
  <li><b>Algoritmo de Dijkstra:</b> Permite calcular la ruta mínima en tiempo entre dos puntos de la red. 
      Complejidad: <i>O((V+E) log V)</i>.</li>
  <li><b>Heurísticas TSP (Vecino Más Cercano + 2-Opt):</b> 
      Usadas en escenarios donde una ambulancia debe recoger múltiples pacientes antes de llegar al hospital.
      No garantizan la solución óptima, pero ofrecen resultados eficientes en tiempos cortos.</li>
</ul>

<hr>

<h2>3. Diseño del dataset</h2>
<ul>
  <li><b>Zona de estudio:</b> San Borja, Lima (extraída de OpenStreetMap con <code>osmnx</code>).</li>
  <li><b>Nodos reales:</b> Hospitales y clínicas (tag <code>amenity=hospital|clinic</code>).</li>
  <li><b>Nodos simulados:</b> 300 pacientes y 50 ambulancias distribuidos en la red vial.</li>
  <li><b>Aristas:</b> Calles con pesos definidos por <code>travel_time</code> (segundos de recorrido).</li>
  <li><b>Tamaño esperado:</b> ~1,000–2,000 nodos para cumplir con los requisitos del TB1 (500 por integrante).</li>
</ul>

<hr>

<h2>4. Plan de implementación</h2>
<ul>
  <li><b>Lenguaje:</b> Python 3.</li>
  <li><b>Librerías:</b> osmnx, networkx, folium, pandas, tkinter.</li>
  <li><b>Avance actual:</b>
    <ul>
      <li>Carga de red vial desde OSM.</li>
      <li>Extracción de hospitales y clínicas reales.</li>
      <li>Simulación de pacientes y ambulancias.</li>
      <li>Implementación de Dijkstra para cálculo de rutas simples.</li>
      <li>Mapa base interactivo con nodos y rutas.</li>
    </ul>
  </li>
  <li><b>Siguientes pasos:</b>
    <ul>
      <li>Integrar heurística TSP para múltiples pacientes.</li>
      <li>Optimizar tiempos de carga guardando grafo en <code>.graphml</code>.</li>
      <li>Generar reportes y métricas de complejidad.</li>
    </ul>
  </li>
</ul>

<hr>

<h2>5. Conclusión preliminar</h2>
<p>
El avance del Hito 1 demuestra que es viable modelar un sistema de derivación médica 
con grafos urbanos reales y algoritmos clásicos de búsqueda de rutas. 
Se cuenta con la base técnica para extender el sistema y cumplir con los requisitos 
del TB1 en los siguientes hitos.
</p>


Aquí tienes un archivo `README.md` completo con los elementos solicitados:

---

# **Minimax y Poda Alfa-Beta**

Este proyecto contiene una implementación del algoritmo **Minimax** y su optimización mediante **Poda Alfa-Beta**. Ambos algoritmos son fundamentales en inteligencia artificial aplicada a juegos de dos jugadores, como el ajedrez o el tres en raya.

---

## **Instrucciones para ejecutar el programa**

### **Requisitos previos**
- Python 3.8 o superior.
- Bibliotecas necesarias (instalar con pip si es necesario):
  - `matplotlib` (para generar gráficos, si se incluyen).

### **Ejecución**
1. Clona este repositorio en tu máquina:
   ```bash
   git clone https://github.com/usuario/repositorio.git
   cd repositorio
   ```
2. Ejecuta el programa principal:
   ```bash
   python main.py
   ```
3. Sigue las instrucciones en la consola para seleccionar el modo de juego:
   - **Jugador vs IA.**
   - **IA vs IA.**

---

## **Explicación del algoritmo utilizado**

### **Minimax**
El algoritmo **Minimax** busca la decisión óptima para un jugador asumiendo que el oponente también juega de manera óptima. En juegos de suma cero:
- Un jugador busca **maximizar** su puntuación.
- El otro busca **minimizar** la puntuación del oponente.

El algoritmo evalúa todos los posibles estados del juego (nodos hoja) y elige la estrategia más favorable.

### **Poda Alfa-Beta**
La **Poda Alfa-Beta** es una optimización del Minimax que reduce la cantidad de nodos evaluados sin alterar el resultado. Utiliza dos límites:
- **Alfa (α):** El mejor valor garantizado para el jugador maximizador.
- **Beta (β):** El mejor valor garantizado para el jugador minimizador.

Si un nodo no puede mejorar el resultado del jugador actual, se detiene su evaluación.

---

## **Explicación teórica**

### **Minimax**
1. **Objetivo:** Maximizar la ganancia del jugador mientras se minimiza la pérdida causada por el oponente.
2. **Funcionamiento:**
   - Representa el juego como un árbol de decisiones.
   - Los nodos hoja tienen valores calculados por una función de utilidad (evaluación del estado).
   - Se recorre el árbol **de abajo hacia arriba**, alternando entre los jugadores:
     - **Max:** Escoge el valor máximo de los hijos.
     - **Min:** Escoge el valor mínimo de los hijos.

### **Poda Alfa-Beta**
1. **Optimización:** Evita evaluar ramas que no afectarán la decisión final.
2. **Estrategia:** Se actualizan los límites de **alfa** y **beta** durante el recorrido:
   - Si un nodo hijo no mejora el valor actual, se detiene la evaluación de sus hermanos.

---

## **Diagrama del árbol de juego (caso simple)**

El siguiente diagrama representa un árbol de decisiones para un juego simple con 2 niveles (Max y Min). Los números en las hojas son los valores de utilidad para el jugador Max:

```
          Max
         /    \
       Min     Min
      / | \   / | \
     3  5  2  9  6  1
```

### **Solución con Minimax:**
- **Max:** Evalúa cada rama.
- Elige el máximo entre los valores obtenidos por los nodos **Min**:
  - **Izquierda:** Min(3, 5, 2) = 2
  - **Derecha:** Min(9, 6, 1) = 1
  - **Resultado:** Max(2, 1) = **2**

### **Solución con Poda Alfa-Beta:**
- Se detienen evaluaciones innecesarias una vez que se cumple la condición de poda.

---

## **Análisis de complejidad**

### **Sin poda alfa-beta (Minimax):**
La complejidad temporal es \(O(b^d)\), donde:
- **\(b\):** Número de movimientos posibles (factor de ramificación).
- **\(d\):** Profundidad del árbol de decisiones.

Ejemplo:
- Para un ajedrez típico: \(b \approx 35\), \(d \approx 6\) → \(35^6 \approx 1,838,265,625\) nodos a evaluar.

### **Con poda alfa-beta:**
En el mejor caso, la complejidad se reduce a \(O(b^{d/2})\). Esto ocurre cuando los nodos son evaluados en un orden óptimo (primero las ramas más prometedoras).

Ejemplo:
- Con los mismos valores (\(b \approx 35\), \(d \approx 6\)):
  \(35^{6/2} = 35^3 = 42,875\) nodos a evaluar.

**Comparación:**
| **Estrategia**   | **Complejidad** | **Nodos evaluados** (aprox.) |
|-------------------|-----------------|-----------------------------|
| Minimax           | \(O(b^d)\)     | 1,838,265,625               |
| Poda Alfa-Beta    | \(O(b^{d/2})\) | 42,875                      |

---

## **Referencias**
- [Minimax en Wikipedia](https://es.wikipedia.org/wiki/Minimax)
- [Poda Alfa-Beta](https://es.wikipedia.org/wiki/Poda_alpha-beta)

---

## **Contribuciones**
¡Las contribuciones son bienvenidas! Si encuentras algún problema o tienes sugerencias para mejorar el proyecto, no dudes en abrir un _issue_ o enviar un _pull request_.

---

## **Licencia**
Este proyecto está bajo la licencia MIT. Consulta el archivo `LICENSE` para más detalles.

--- 

Si necesitas ayuda con el código para construir este programa, no dudes en pedírmelo. 🚀

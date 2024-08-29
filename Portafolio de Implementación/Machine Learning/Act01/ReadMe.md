# **Actividad Individual**

### **Datos personales**
- **Sofía Cantú** | Matrícula: A01571120

### **Actividad 1: Implementación de una técnica de aprendizaje máquina sin el uso de un framework**

Nombre completo de la actividad: Momento de Retroalimentación: Módulo 2 Implementación de una técnica de aprendizaje máquina sin el uso de un framework. (Portafolio Implementación)

Challengue escogido: Week01 Challenge

El codigo correspondiente a la actividad se ha subido en esta carpeta como "M2_A1_Challenge.ipynb" y evidencia en pdf llamada "M2_A1_Challenge.pdf". 

A continuación, se presenta una imagen de los resultados de la primera versión:

<p align="center">
  <img src="/ArchivosExtras/M2_A1_Graficas.png" alt="Resultados de la Actividad 1" width="800"/>
</p>



## Segunda entrega

Para la segunda versión, se implementaron los siguientes cambios:

### 1. Ampliación del rango de valores para la tasa de aprendizaje

Originalmente el código probaba dos valores para la tasa de aprendizaje. Se amplió el rango de valores:

```python
# Anterior
alphas = [0.001, 0.0001]
# Nuevo
alphas = [1, 0.1, 0.01, 0.001, 0.0001, 0.00001]
```

### 2. Inicialización de Parámetros Más Informada:
El código solía establecer los parámetros de theta aleatoriamente. Ahora, se utiliza una inicialización basada en el cálculo de la covarianza y la varianza, lo que proporciona una mejor aproximación inicial.
```python
# Anterior
theta = np.random.randn(2, 1)

# Nuevo
theta[1] = np.cov(X_train.flatten(), y_train.flatten())[0, 1] / np.var(X_train)
```

### 3. Mejora en el Número de Iteraciones:
El número de iteraciones era un valor fijo de 10,000. Se mejoró la implementación de la función gradient_descent, la cual detiene el entrenamiento si el cambio en el costo entre iteraciones es menor que un umbral definido, manteniendo un máximo de 10,000 iteraciones.
```python
# Antes
n_iterations = 10000

# Ahora
n_iterations = 10000
optimal_alpha = find_optimal_alpha(X_train, y_train, alphas, n_iterations)
```

### 4. Documentación de los Criterios de Selección de Variables:
Se añadió documentación detallada en el código acerca de los criterios utilizados para la selección de las variables.

A continuación, se presenta una imagen de los resultados de la segunda versión versión:

<p align="center">
  <img src="/ArchivosExtras/M2_A1_GraficasNuevas.png" alt="Resultados de la Actividad 1" width="800"/>
</p>

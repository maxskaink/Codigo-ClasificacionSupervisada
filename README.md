
# Modelo de Regresión Logística en el Estudio de la Natalidad en Colombia

Este proyecto tiene como objetivo principal analizar datos sobre natalidad en Colombia, utilizando técnicas de clasificación supervisada. A través de modelos estadísticos como **Support Vector Classification (SVC)** y **K-Nearest Neighbors (KNN)**, buscamos predecir si una madre tendrá más de un hijo, basándonos en características extraídas de datos oficiales.

---

## Tabla de Contenidos
- [Descripción del Proyecto](#descripción-del-proyecto)
- [Características de los Datos](#características-de-los-datos)
- [Metodología](#metodología)
- [Resultados](#resultados)
- [Requisitos](#requisitos)
- [Instrucciones de Uso](#instrucciones-de-uso)
- [Autores](#autores)
- [Referencias](#referencias)

---

## Descripción del Proyecto
El proyecto utiliza datos recolectados y publicados por el Departamento Administrativo Nacional de Estadística (DANE) en el año 2015, bajo el cumplimiento de la Ley 1712 de 2014. Estos datos incluyen características demográficas y de salud materna, como:
- **Área de nacimiento**
- **Peso y talla del recién nacido**
- **Edad de la madre**
- **Tipo de parto**
- **Número de consultas prenatales**
- Entre otros.

El objetivo es construir modelos predictivos que permitan explorar relaciones clave entre estas características y la probabilidad de que una madre tenga más de un hijo.

---

## Características de los Datos
### Variables Principales
Los datos están codificados para facilitar su manipulación. Algunas variables relevantes incluyen:
- **AREANAC**: Área del nacimiento (e.g., cabecera municipal, zona rural dispersa).
- **PESO_NAC**: Peso del recién nacido categorizado en rangos.
- **TALLA_NAC**: Talla del recién nacido.
- **EDAD_MADRE**: Edad de la madre en intervalos de cinco años.
- **N_HIJOSV**: Número de hijos vivos de la madre (variable objetivo transformada en binaria para clasificación).

### Procesamiento de Datos
- Filtrado de datos por región (departamento del Cauca).
- Escalado de características numéricas usando **MinMaxScaler**.
- Imputación de valores faltantes mediante la estrategia de media.
- Transformación de la variable objetivo en un formato binario (1: más de un hijo, 0: solo un hijo).

---

## Metodología
### Clasificación Supervisada
Se emplearon los siguientes modelos:
1. **Support Vector Classification (SVC)**:
    - Kernel: lineal, radial, polinómico.
    - Optimización de hiperparámetros mediante Grid Search.
2. **K-Nearest Neighbors (KNN)**:
    - Selección del valor óptimo de vecinos (`k`).
    - Pruebas con diferentes métricas de distancia.

### Validación
Se aplicó validación cruzada para evaluar la capacidad predictiva y generalización de los modelos.

---

## Resultados
- **Modelo SVC**: 
  - Precisión global: 75.5%
  - Mejor kernel: polinómico.
  - Hiperparámetros optimizados: `C=10`, `gamma=scale`.
- **Modelo KNN**:
  - F1-score: 0.80.
  - Distancia: Euclidiana.
  - Número óptimo de vecinos: `k=31`.

### Visualizaciones
El análisis incluye:
- Distribuciones de variables clave.
- Matriz de correlación.
- Boxplots de relaciones entre características y la variable objetivo.

---

## Requisitos
- Python 3.7 o superior.
- Librerías necesarias:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `scikit-learn`

---

## Instrucciones de Uso
1. Clonar este repositorio:
    ```bash
    git clone https://github.com/tu_usuario/regresion-logistica-natalidad.git
    ```
2. Instalar las dependencias:
    ```bash
    pip install -r requirements.txt
    ```
3. Ejecutar el script principal para entrenar y evaluar los modelos:
    ```bash
    python main.py
    ```

---

## Autores
- **Miguel Ángel Calambás Vivas**
- **Esteban Santiago Escandón Causaya**

---

## Referencias
- Departamento Administrativo Nacional de Estadística (DANE). *Estadísticas Vitales - EEVV - 2015*. [Enlace](https://microdatos.dane.gov.co/index.php/catalog/475/get-microdata).
- Scikit-learn Developers. *Documentación oficial*. [Enlace](https://scikit-learn.org/1.5/modules/model_evaluation.html).
- "¿Primera vez con Datos Abiertos? Aquí te contamos qué son y cómo usarlos". Datos Abiertos Colombia. [Enlace](https://www.datos.gov.co/stories/s/-T-primera-vez-con-Datos-Abiertos-Aqu-te-contamos-/smn2-7atz).
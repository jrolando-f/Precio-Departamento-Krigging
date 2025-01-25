# Estimación de Precios de Departamentos y Precio por Metro Cuadrado en el AMBA mediante Regression Kriging

## Descripción
Este proyecto tiene como objetivo estimar los precios de departamentos y el precio por metro cuadrado en el Área Metropolitana de Buenos Aires (AMBA) utilizando **Regression Kriging**, un método geoespacial avanzado que combina un modelo lineal con interpolación espacial para predecir precios basados en variables geográficas y socioeconómicas.

## Objetivos
- Estimar el precio de los departamentos y el precio por metro cuadrado utilizando Regression Kriging.
- Analizar cómo la ubicación geográfica dentro del AMBA y las covariables afectan los precios de los departamentos.
- Evaluar la influencia de variables como la distancia al transporte público y espacios verdes en los precios.

## Integrantes
- Nazareno Magallanes
- Julián Rolando

## Profesor
- Rafael Grimson

## Año
2024

## Herramientas y Tecnologías
- **Lenguaje de programación:** Python
- **Bibliotecas:**
  - NumPy, Pandas: Para manejo y manipulación de datos.
  - Matplotlib, Seaborn: Para visualización de datos.
  - PyKrige, scikit-learn: Para implementar el modelo de Regression Kriging.
- **Software de SIG:** QGIS (para procesamiento de datos espaciales y creación de cuadrículas).

## Procedimiento

### 1. Obtención de los Datos
Se obtuvieron los datos de diferentes fuentes:
- Precios de departamentos con covariables (Properati).
- Datos geoespaciales de estaciones de subte, paradas de colectivos, estaciones de tren, y espacios verdes (QGIS/OpenStreetMap).
- Polígonos del AMBA (Datos abiertos PBA).

### 2. Preparación de los Datos
- Se procesaron y georeferenciaron los datos utilizando QGIS y SQL espacial.
- Se calcularon distancias a diversas infraestructuras, como estaciones de transporte público y espacios verdes.

### 3. Análisis Exploratorio de los Datos
- Visualización y limpieza de los datos (eliminación de valores nulos y outliers).
- Análisis de correlaciones entre las variables y su influencia en el precio de los departamentos.

### 4. Modelado
- Se entrenó un modelo de regresión lineal con regularización **Lasso** para explorar la importancia de las variables predictoras.
- Se utilizó **Elastic Net** para la parte determinística y **Ordinary Kriging** para la parte espacial.

### 5. Evaluación y Resultados
- El modelo fue evaluado mediante métricas como el **Error Absoluto Medio (MAE)**, **Error Cuadrático Medio (MSE)** y **R²**.
- Se visualizó la predicción del precio por metro cuadrado en el AMBA utilizando QGIS.

## Resultados

### Modelo de Regresión:
- **Componente determinística**: Regresión lineal con regularización **Elastic Net**.
  - **Parámetros**: alpha, l1_ratio.
  - **Variables relevantes**: ambientes, baños.

- **Componente espacial**: Ordinary Kriging con modelo gaussiano.
  - **Parámetros**: nugget, sill, range.

### Métricas de Evaluación:
- **MAE**:
- **MSE**:
- **R²**

### Visualización:
- Predicción espacial del precio por metro cuadrado, destacando áreas con mayor densidad poblacional.

## Limitaciones
- El modelo se entrenó con una muestra reducida (15,000 datos) por limitaciones computacionales.
- Algunas zonas con escasez de datos presentaron proyecciones menos precisas.

## Conclusiones
- Aunque la proximidad a transporte público y espacios verdes tiene un impacto en los precios, otros factores como la superficie y la antigüedad de los edificios son más determinantes.
- **Regression Kriging** es una herramienta poderosa para capturar tanto efectos espaciales como determinísticos, aunque la calidad y cobertura de los datos es crucial para obtener mejores resultados.

## Instalación

### Requisitos:
- Python 3.x
- Librerías necesarias:
  ```bash
  pip install numpy pandas matplotlib seaborn scikit-learn pykrige geopandas qgis

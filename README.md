# Evaluación de LLMs con Hugging Face

## Resumen del Proyecto
Este proyecto evalúa y compara modelos de NLP en tareas fundamentales (resumen, clasificación, traducción, generación de texto, zero-shot y few-shot learning) utilizando pipelines de Hugging Face. Se mide el desempeño de cada modelo en términos de parámetros, tamaño en memoria, tiempo de inferencia y métricas específicas (ROUGE, BLEU, accuracy, perplexidad, etc.).

## Objetivos
- Automatizar la evaluación de modelos de lenguaje en múltiples tareas.
- Comparar modelos en diferentes configuraciones (pequeño, mediano, grande).
- Extraer insights a partir de métricas cuantitativas y visualizaciones.
- Registrar y exportar los resultados para análisis posterior.

## Arquitectura y Flujo de Trabajo
- **Preparación del Entorno:**  
  Instalación y configuración de las librerías necesarias (ver [requirements.txt](requirements.txt)).

- **Estructuración del Benchmark:**  
  Se utiliza un DataFrame MultiIndex para registrar:
  - Nombre del modelo
  - Tiempo de inferencia
  - Tamaño en GB
  - Cantidad de parámetros
  - Métrica asociada (ROUGE, BLEU, accuracy, perplexidad)

- **Ejecución de Tareas:**
  - **Summarization:** Uso de T5 y BART.
  - **Text Classification:** Evaluación de sentimientos (poemas, GLUE MNLI).
  - **Translation:** Traducción inglés-español y alemán-inglés con la métrica BLEU.
  - **Text Generation:** Generación de texto con GPT-2 y DialoGPT, midiendo la perplexidad.
  - **Zero-shot Classification:** Clasificación de sentimientos sin reentrenamiento.
  - **Few-shot Learning:** Generación de texto mediante prompt engineering (GPT-Neo, BioGPT).

- **Registro y Exportación:**  
  Los resultados se almacenan en un DataFrame y se exportan a archivos Excel (`benchmark.xlsx` y `benchmark_v2.xlsx`) que puedes abrir dentro de este repo.

## Instrucciones de Ejecución

### 1. Clonar el repositorio
```bash
git clone https://github.com/Daarwinmendez/LLM-Applications.git
cd LLM-Applications
```
### 2. Instalar dependencias
```
pip install -r requirements.txt
```

### 3. Ejecutar el Notebook o Script
* En Jupyter Notebook / Colab:
Abre el archivo main.ipynb y ejecútalo celda por celda.
* Como Script Python:
Si deseas ejecutar el proyecto como script, asegúrate de que el entorno esté configurado, descarga el ejecutable y ejecuta:

```bash
python main.py
```
(Verifica el nombre del script según corresponda.)

### 4. Visualización y Análisis
Los resultados se exportarán en archivos Excel (benchmark.xlsx y benchmark_v2.xlsx) en la raíz del proyecto.
Se generarán gráficos y matrices de confusión durante la ejecución para facilitar el análisis visual de los resultados.

## Tecnologías Utilizadas

* Lenguaje: Python
* Entorno: Jupyter Notebook / Google Colab
* Librerías: Hugging Face Transformers, Datasets, Evaluate, Pandas, NumPy, Matplotlib, Seaborn, TensorFlow, PyTorch, entre otras.

## Resultados y Conclusiones
El enfoque modular del proyecto permite una evaluación integral de modelos de NLP, facilitando la identificación de fortalezas y áreas de mejora. Los resultados obtenidos respaldan decisiones informadas para la selección y optimización de modelos en aplicaciones de procesamiento de lenguaje natural.


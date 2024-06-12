# Sistema de Recomendación de Películas Basado en Clasificación de Textos y Estilometría
Presentación del proyecto final de la materia de procesamiento de lenguaje natural de la maestría en ciencia de datos de la Universidad Panamericana
## Descripción del Proyecto

Este proyecto implementa un sistema de recomendación de películas basado en la clasificación de textos y el análisis estilométrico. Utilizando subtítulos de películas en español, organizados por género, el sistema puede recomendar películas basadas en el género y el estilo del texto de entrada.

## Estructura del proyecto

- **code/**: Carpeta con el código necesario para llevar a cabo el proyecto

- **dataset/**: sets de datos para llevar a cabo el proyecto

- **output/**: Archivos de salida del proyecto (base de datos procesada y modelos entrenados)



## Objetivos

1. **Clasificación de Textos:** Clasificar los subtítulos de las películas en géneros específicos utilizando técnicas de procesamiento de lenguaje natural (NLP).
2. **Análisis de Estilometría:** Analizar el estilo de los textos mediante q-gramas y otras técnicas estilométricas.
3. **Sistema de Recomendación:** Desarrollar un sistema que sugiera películas basadas en el género y el estilo del texto de entrada.



## Preprocesamiento de Texto

El preprocesamiento del texto incluye:

1. **Limpieza de Texto:** Eliminación de etiquetas HTML y caracteres especiales, y conversión del texto a minúsculas utilizando BeautifulSoup y expresiones regulares.
2. **Vectorización:** Transformación del texto en una representación numérica utilizando TfidfVectorizer.

## Modelos de Clasificación

Se entrenaron y evaluaron tres modelos de clasificación de textos:

1. **Naive Bayes**
2. **Random Forest**
3. **Support Vector Machine (SVM)**

El modelo SVM mostró el mejor rendimiento y fue seleccionado para el sistema de recomendación.

## Análisis de Estilometría

Utilizamos q-gramas para analizar el estilo de los textos. Esta técnica permite capturar patrones de estilo basados en la frecuencia y secuencia de caracteres.

## Sistema de Recomendación

El sistema recomienda películas de dos formas:

1. **Basada en Género:** Utiliza el modelo SVM para predecir el género del texto de entrada y recomienda películas del mismo género.
2. **Basada en Estilo:** Calcula la similitud de estilo entre el texto de entrada y los subtítulos de todas las películas, recomendando las más similares en estilo.

## Uso

### Preprocesamiento de Datos

```bash
python src/preprocessing.py --data_path data/subtitulos --output_path data/processed_data.csv

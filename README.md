# Aplicación Interactiva de Análisis Ideológico Basado en NLP

## Universidad del Valle de Guatemala  
### Facultad de Ingeniería  
### Departamento de Ciencias de la Computación  

### Feria Científica UVG 2024 
**Autores:**  
- Alejandro José Gómez (20347)  
- Jorge Caballeros (20009)  
- Pablo Escobar (20936)

---

## Descripción del Proyecto

Este proyecto aplicado tiene como objetivo principal desarrollar una **aplicación interactiva** que permita a los usuarios identificar su **posición ideológica** utilizando **técnicas de procesamiento de lenguaje natural (NLP)**. Este sistema está dirigido principalmente a personas que se consideran **indecisas** o **apolíticas**, ofreciéndoles una herramienta para descubrir y comprender mejor sus propias creencias políticas y sociales.

### Problema que Resuelve

Muchas personas carecen de claridad sobre su ubicación en el **espectro político**. Esto puede deberse a:
- Falta de conocimiento o reflexión sobre temas políticos.
- Polarización de los medios.
- Incapacidad de conectar sus creencias con las etiquetas políticas comunes (izquierda, derecha, libertario, etc.).

Este problema afecta el **compromiso cívico** y la **participación política**, limitando su involucramiento en los procesos democráticos. 

### Solución Propuesta

La aplicación ofrece una **encuesta interactiva** en la que los usuarios pueden responder preguntas clave sobre temas políticos y sociales. Las respuestas pueden ser abiertas, permitiendo el uso de **NLP** para analizar los textos y asignar una **orientación ideológica** basada en sus respuestas.

La solución incluye los siguientes componentes:

- **Encuesta Interactiva con Preguntas Clave**: 
  Se plantean preguntas sobre temas relevantes como economía, derechos civiles, política exterior, y más. Las respuestas ayudan a identificar tendencias ideológicas.

- **Análisis de Texto con NLP**: 
  Las respuestas abiertas del usuario son procesadas mediante técnicas de **procesamiento de lenguaje natural (NLP)**, detectando palabras clave, entidades y sentimientos que permiten clasificar las tendencias ideológicas.

- **Visualización en el Mapa Ideológico**: 
  Al finalizar el análisis, la aplicación presenta al usuario una **visualización interactiva** de su posición ideológica en un gráfico bidimensional, que refleja tanto la dimensión izquierda-derecha como otras dimensiones relevantes como libertario-autoritario.

---

## Técnicas de NLP Utilizadas

Este proyecto utiliza diversas **técnicas avanzadas de NLP** que permiten realizar el análisis ideológico de las respuestas. A continuación se detallan las técnicas más relevantes:

### 1. **Procesamiento de Lenguaje Natural con `spacy`**  
Utilizamos la librería **`spacy`** para realizar **tokenización** y **análisis de entidades nombradas** (NER - Named Entity Recognition). Esta técnica permite identificar elementos importantes en las respuestas del usuario, como entidades geopolíticas (`GPE`), organizaciones (`ORG`), y más. Esto es esencial para detectar menciones a gobiernos, instituciones o políticas que puedan influir en la interpretación ideológica.

### 2. **Clasificación Zero-Shot con `transformers` y BART**  
Empleamos el modelo **BART (Bidirectional and Auto-Regressive Transformers)**, una técnica moderna de **NLP** que permite realizar **clasificación Zero-Shot**. Este modelo es capaz de asignar etiquetas ideológicas (por ejemplo, "izquierda", "derecha", "libertario", etc.) a las respuestas del usuario sin haber sido entrenado específicamente en esos datos. Esto nos permite obtener predicciones rápidas y precisas sobre las tendencias políticas de los usuarios.

### 3. **Análisis de Sentimiento con DistilBERT**  
DistilBERT es otro modelo de **transformers** utilizado para detectar el **sentimiento** en las respuestas de los usuarios. Esto nos permite evaluar si el usuario tiene una perspectiva positiva o negativa sobre temas clave, lo que complementa la clasificación ideológica. Por ejemplo, si un usuario expresa un sentimiento negativo sobre las empresas, esto puede influir en su clasificación como más cercano a la izquierda económica.

### 4. **Vectorización de Texto con TF-IDF**  
Usamos **TF-IDF (Term Frequency-Inverse Document Frequency)** para convertir las respuestas textuales en vectores numéricos que luego son utilizados en un modelo de **regresión logística supervisado**. Este enfoque clásico en **NLP** permite identificar palabras clave importantes en las respuestas, asignándoles un peso basado en su relevancia para determinar la ideología del usuario.

### 5. **Modelo Supervisado (Regresión Logística)**  
El modelo de **regresión logística** supervisado utiliza las características extraídas de TF-IDF para predecir la ideología política basada en las respuestas del usuario. Aunque es un enfoque clásico, sigue siendo efectivo para tareas de clasificación como esta.

### 6. **Reglas Personalizadas con NLP**  
Para ajustar los resultados, también hemos definido **reglas personalizadas** que se activan cuando detectamos palabras clave específicas en las respuestas. Estas reglas permiten ajustar los puntajes ideológicos, haciendo el modelo más sensible a temas particulares. Por ejemplo, si se menciona "redistribución", el puntaje de la izquierda aumenta.

---

## Flujo de la Aplicación

1. **Entrada del Usuario**:
   - Los usuarios responden una serie de preguntas abiertas sobre su perspectiva política.
   
2. **Procesamiento y Análisis**:
   - El sistema utiliza **NLP** para analizar las respuestas del usuario. Esto incluye:
     - Detección de entidades (gobiernos, empresas, etc.).
     - Análisis de sentimiento.
     - Clasificación Zero-Shot (BART) para obtener etiquetas ideológicas.
     - Aplicación de reglas personalizadas.

3. **Visualización de Resultados**:
   - Una vez que el análisis está completo, el sistema presenta los resultados en un **gráfico bidimensional** que muestra la posición ideológica del usuario, con dimensiones de izquierda-derecha y libertario-autoritario.

---

## Justificación del Proyecto Aplicado

Este proyecto aborda un problema real: la **falta de autoconocimiento político** entre los ciudadanos. Al proporcionar una herramienta accesible que utiliza **NLP** para analizar creencias y opiniones políticas, se fomenta una mayor **participación cívica** y se ayuda a los usuarios a comprender mejor sus propios valores en el contexto del espectro político.

Además, esta solución es aplicable en una variedad de contextos, como:
- **Educación Cívica**: Permitiendo a los estudiantes reflexionar sobre sus creencias políticas.
- **Compromiso Político**: Ayudando a los ciudadanos a tomar decisiones más informadas en elecciones o debates.
- **Investigación Social**: Permitirá a investigadores analizar tendencias ideológicas en poblaciones grandes.

---

## Equipo de Desarrollo

- **Alejandro José Gómez** (20347): Líder del equipo, responsable de la arquitectura principal del sistema y la integración de modelos **NLP**.  
- **Jorge Caballeros** (20009): Responsable del análisis de datos y pruebas del sistema, colaboró en la implementación de los modelos supervisados.  
- **Pablo Escobar** (20936): Encargado de la visualización de resultados y optimización del procesamiento de lenguaje natural, así como de la implementación del análisis de sentimientos.

---

## Bibliografía

Grimmer, J., & Stewart, B. M. (2013). Text as Data: The Promise and Pitfalls of Automatic Content Analysis Methods for Political Texts. *Political Analysis, 21*(3), 267-297. doi:10.1093/pan/mps028.

Iyyer, M., Enns, P., Boyd-Graber, J., & Resnik, P. (2014). Political Ideology Detection Using Recursive Neural Networks. In Proceedings of the 52nd Annual Meeting of the Association for Computational Linguistics (pp. 1113-1122). doi:10.3115/v1/P14-1100.

Sim, Y., Smith, N. A., & Wallace, B. C. (2013). Discovering Political Polarization in Media. In Proceedings of the 51st Annual Meeting of the Association for Computational Linguistics (pp. 415-424). doi:10.3115/v1/P13-1041.

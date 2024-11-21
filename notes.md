# Notas

## Reto 01

- **¿Qué es el principio de prompting iterativo?**
  - Es una técnica que consiste en ir añadiendo información al prompt de manera iterativa para guiar al modelo a completar una tarea específica.
- **¿Qué hiperparámetros podrías ajustar para hacer que la respuesta sea más diversa en términos de lenguaje?**
  - `temperature`
- **¿Qué técnica de ‘prompt engineering’ podrías usar para ayudar al modelo a completar tareas difíciles como problemas matemáticos?**
  - Añadir ejemplos de cómo resolver problemas matemáticos.

## Reto 02
- **¿Cuáles son las capacidades de cada modelo de Azure OpenAI?**
  - `text-analytics`:
    - `sentiment-analysis`
    - `key-phrases-extraction`
    - `named-entity-recognition`
    - `language-detection`
  - `text-generation`:
    - `text-completion`
    - `text-generation`
    - `text-summarization`
    - `text-translation`
- **¿Cómo seleccionar el modelo adecuado para tu aplicación?**
  - Dependiendo de la tarea que se quiera realizar.
- **¿Qué modelo elegirías para resumir prompts?**
  - `text-summarization`
- **¿Qué modelo elegirías para generar nuevos nombres?**
  - `text-generation`
- **¿Cómo recuperar embeddings?**
  - Usando la API de `text-analytics`.
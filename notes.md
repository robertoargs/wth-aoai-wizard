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

## Reto 03
- **¿Por qué es importante la fundamentación y cómo puedes fundamentar un modelo LLM?**
  - Porque ayuda a entender cómo funciona el modelo y cómo se puede mejorar.
- **¿Qué es un límite de tokens?**
  - Es el número máximo de tokens que se pueden usar en un prompt.
- **¿Cómo puedes manejar los límites de tokens?**
  - Usando la técnica de `prompt engineering`.
- **¿Cuáles son las técnicas de segmentación?**
  - `windowing`
  - `sliding window`
  - `prompt engineering`
- **¿Qué ayudan a lograr los embeddings?**
  - A entender cómo se relacionan las palabras en un texto.

# Apuntes

1. ¿Qué es Prompting Engineering?
Son técnicas que se utilizan para guiar al modelo a que nos de una respuesta específica.

2. ¿Qué son los tokens?
La unidad de facturacion de Azure OpenAI es por tokens.

3. ¿Qué es un contexto?
Es la información que se le da al modelo para que pueda generar una respuesta.

## Reto 01 - Minuto 8:00
Parámetros que necesitan los modelos GPT

- Temperatura: cuando hacemos pregunta a modelos GPT podemos utilizar temperatura para que GPT genere una respuesta altamente creativa o muy enfocda o conservadora. Un valor bajo de temperatura es conservadora, coherente y determinista. Ejemplo quien descubrio america GPT dira fue descubierta por Cristobal Colon, es decir, usa respuestas muy concisas o enfocadas. Un valor alto hara que la respuesta sea creativa o diversa, al preguntar quien descrubiro america dira fue por Cristobal COlon que era un navegante Genoves que buscaba llegar a las Indias, etc crea una respuest diversa y entre mas tokens se genera puede haber un error. La temperatura se afecta dependiendo de lo que quiera hacer, si quiero un resumen uso temperatura alta, si deseo algo como respuestas simples uso temperatura baja. SIno puedo usar una temperatura media.

- Top P: cuando pregunto quien descubrio america habra coleccion de tokens. Si hay un universo de 1000 palabras. 0.5 significa la mitad o 50 palabras mas probables a elegir y las usara para construir su respuesta. Usan lo mismo asi que no se deberian usar ambios al mismo tiempo. Es como tener una bolsa mas grande o mas pequeña de palabras para elegir.Es como el vocabulario disponible para generar una respuesta.

Top P es la probabilidad de que el modelo genere una respuesta. Si pongo 0.5 el modelo generara una respuesta con 50% de probabilidad. Si pongo 0.9 el modelo generara una respuesta con 90% de probabilidad. Si pongo 1 el modelo generara una respuesta con 100% de probabilidad. Si pongo 0.1 el modelo generara una respuesta con 10% de probabilidad. Si pongo 0.01 el modelo generara una respuesta con 1% de probabilidad. Si pongo 0.001 el modelo generara una respuesta con 0.1% de probabilidad. Si pongo 0.0001 el modelo generara una respuesta con 0.01% de probabilidad. Si pongo 0.00001 el modelo generara una respuesta con 0.001% de probabilidad. Si pongo 0.000001 el modelo generara una respuesta con 0.0001% de probabilidad. Si pongo 0.0000001 el modelo generara una respuesta con 0.00001% de probabilidad. Si pongo 0.00000001 el modelo generara una respuesta con 0.000001% de probabilidad. Si pongo 0.000000001 el modelo generara una respuesta con 0.0000001% de probabilidad. Si pongo 0.0000000001 el modelo generara una respuesta con 0.00000001% de probabilidad. Si pongo 0.00000000001 el modelo generara una respuesta con 0.000000001% de probabilidad. Si pongo 0.000000000001 el modelo generara una respuesta con 0.0000000001% de probabilidad. Si pongo 0.0000000000001 el modelo generara una respuesta con 0.00000000001% de probabilidad. Si pongo 0.00000000000001 el modelo generara una respuesta con 0.000000000001% de probabilidad. Si pongo 0.000000000000001 el modelo generara una respuesta con 0.0000000000001% de probabilidad. Si pongo 0.0000000000000001 el modelo generara una respuesta con 0.00000000000001% de probabilidad

- Max tokens: limitamos la salida, truncamos la salida a ciertos tokens si le rpegunto a GPT quien descrebiro america y pongo max tokens 20 entonces me empieza a decir america fue descubierta por navegante genoves y se corta porque me llega a los 20 tokens.

- Frequency penalty: es un valor que afecta si podemos repetir tokens o no. Cada token tiene unba probabilidad de ser generado. A valor mas alto de frequency penalty la palabra Cristobal va a disminuir su probabilidad de ser elegida proque queremos evitar que repita otkens, se puede repetir pero se puede aplciar unba penalidad por repetir un token que ha pasado antes, un balor negativo promoveria que se repita los tokens. Queremos con esto que la slaida sea mas diversa y que no haya repeticion de tokens.

- Un user y un assitant

- Prompt engineerings es conjuntio de tecnicas que pdoeso suar par QUE MODELOS got RESPONDAN PREGUTNAS DE MANERA CONCISA, CENTRADA Y PARA LO QUE EL SUSUAIRO ESPER.A. Dos cosas es genera un resumen y otra, incluyeme un resumen con causas, analisis, consecuencias, para poder tener una respuesta mas completa.

## Reto 02
Compararemos salidas, cuantos tokens consumen cada peticion y tambien cuanto tiempo se tardan. GPT-4 es un modelo mas poderoso que se tarda mas, se toma su tiempo para responder una pregunta o realizar una instruccion porque procesa mas parametros, es mas costoso pero las respuestas son mucho mejores. El GPT-35-turbo significa que es mas veloz a costa de la precision, es decir, que las respuestas tienen un nivel de confiabildiad inferior con respectoa a GPT-4
## Reto 03
- Grounding: es una tecnica fundamentacion quiere decir que cuando preguntamos al modelo GPT la respuesta que nos da que este fundamentada, aterrizada conrelacion a una fuente de informacion. puede ser nuestro propio conocimiento o otra fuente. El GPT-35-turbo llega hasta septiembre 2021 y GPT-4 abril de 2023. El objetivo es que la respuesta obtenida para algo futuro esta respuesta se obtiene gracias a pasarle informacion adicional. Esto no es entrenar un modelo es dar contexto. Se puede usar el role system para proporcionar ese contexto. Groundin resuelve la limitante de tener eventos al futuro, puedo hacer preguntas de documentos PDF entre otros. Lo que se aplica a nivel de proyectos real es RAG que viene a ser el grounding hecho con RAG. Grounding se relaciona con todo

- Token son parte de una plabra no son silabas ni toda la palabra. Estos son los datos de entrada que acepta el LLM no es el texto son los tokens. Para esto usaremos la libreria tiktokens.

- Chunkings: si mando muchosm mas tokens de los que puede soportar una lalmada GPT hay error. No puedo mandar un PDF completo. Hay que enviar todo por trozos o segmentacion, esto es chinking. En vez de vectorizar todo, divido el texto en parrafos, palabras, oraciones o tecnicas mas heuristicas. Chunking es divir texto grande en fragmentos mas pequeños

- EMbeddings: tenemos PDF grandote y usuario hace consulta. Tenemsoq ue de alguna maner pasar unicamente los chunks relevcantes o significativos. Entonces debemos tener un mecanismo para poder hacer comparaciones., Esas comparaciones no van a ser a travez de texot sino valores numericos, mas expecicamente, vectores. Para eso existen los embeddings. eSTO es una representacion vectorial. No importa la longitud de kla cadena de texto que envie, el punto es que se genera vectores y eso se hace porque eventualmente vamosa  comparar vectores contra el vector de la consulta. Por una texnica que se llama similitud coseno y si eso es cercano a 1 quiere decir que la consulta y el chunk o documento hablan de temas parecidos, es decir, el documento es relevante para la pregunta. O si es cercano a cero que no habnlan del mismo tema. Vector captura significado semantico de ese texto.
Puedo definri que chunks se acercan a mi consulkta a traves de los embeddings.

## Reto 04
## Reto 05
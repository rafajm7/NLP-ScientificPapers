# NLP-ScientificPapers

El objetivo de este repositorio consiste en la extracción y análisis de documentos científicos de Google Scholar a partir de un perfil de interés. Este perfil de interés se define mediante varias consultas textuales que se utilizarán para buscar en Google Scholar los artículos relacionados con ese perfil, extraerlos, parsear el PDF, analizarlo (extraer tópicos) y construir un buscador sobre los documentos extraídos. El proyecto está realizado en Python.

### Pasos a seguir

1. El primer paso consiste en conseguir acceso a los datos que se quieren tratar. Para poder extraer datos de un perfil determinado, vamos a usar la librería ![scholarly](https://pypi.org/project/scholarly/) de Python. Usando este paquete, podemos obtener la información básica de los perfiles considerados.

2. Una vez tenemos esos metadatos sobre los documentos científicos que cumplen con nuestro perfil, extraemos toda la información posible contenida en los mismos. Por ejemplo, además de obtener el título del artículo, si está disponible el abstract, será necesario extraerlo, y si hay un hiperenlace a un archivo PDF será necesario extraerlo automáticamente y parsearlo para obtener texto, para lo que usaremos la librería *pdfMiner*. 

3. Para poder analizar estos documentos, los guardamos en un formato adecuado, definiendo un esquema JSON. 

4. Realizamos un procesamiento del corpus obtenido para vectorizar la colección y mostrar los términos más "centrales" de los documentos, es decir, los que tengan un mayor valor de TF-IDF (term frequency - inverse document frequency).

5. Una vez ya hemos procesado el corpus, podemos hacer uso de otras librerías para hacer un análisis más detallado del mismo. En concreto, *Gensim* se puede usar para realizar una extracción no supervisada de tópicos existentes en el corpus extraído, así como para su posterior visualización. Otra medida que hemos realizado es la indexación de los documentos recuperados para poder realizar rápidamente búsquedas sobre los mismos.

Este proyecto se presenta en formato de Jupyter Notebook con explicaciones detalladas, adjuntando también un fichero .html donde podemos ver el resultado de la ejecución de cada celda.

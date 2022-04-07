# Selenium Nodes

Remote browser nodes to run jobs received by Selenium Hub in a scalable way

## Usar diferentes versiones simultáneamente

Es posible lanzar servicios para generar nodos en versiones diferentes a las especificadas en las variables del proyecto, que convivan con los nodos ya en ejecución y unidos al mismo Selenium Hub. Para ello, se debe lanzar un nuevo pipeline especificando un nuevo valor para algunas variables.

Por ejemplo, para lanzar 2 nuevos nodos de Google Chrome en su versión v99.0 (pero ninguno de Mozilla Firefox), debemos definir las siguientes variables:

* **STACK**: `testing-chrome-v99`.
* **DD_CHROME_IMAGE_TAG**: `99.0`.
* **DD_CHROME_HOSTNAME_PREFIX**: `chrome-v99`.
* **DD_CHROME_REPLICAS**: `2`.
* **DD_FIREFOX_REPLICAS**: `0`.

En definitiva, especificamos un stack diferente para no sobreescribir a los nodos en ejecución, diferenciamos algunos valores de Chrome (versión, hostname y réplicas) y evitamos que se lance ningún nodo de Firefox (se creará el servicio, pero con 0 replicas).

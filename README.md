# Nunca entendí los Closures en JavaScript
## Hasta que alguien me lo explicó así...

![1_1vMy563vz6LA_67VrzeT9g](https://user-images.githubusercontent.com/62315823/91623546-3ef4de00-e972-11ea-87d8-7f81f5742e3c.png)

Como el título dice, los Closures en JavaScript siempre fueron algo misteriosos para mí. Leí muchos artículos, use Closures en mi trabajo y hasta usé Closures sin siquiera saber que estaba usando Closures.

Recientemente fui a una charla donde alguien me lo explicó de manera tal que finalmente lo entendí. Ahora, intentaré explicarlo de la misma manera. Doy los creditos a los muchachos de CodeSmith y su serie "JavaScript: The Hard Parts".

## **Antes de que empecemos**

Es importante entender algunos conceptos antes de entender realmente los Closures. Uno de ellos es el ***Execution Context***.

En el siguiente artículo encontrarás buenas definiciones sobre el Execution Context. Citandolo:

> Cuando corres código en JavaScript, el *enviroment* en el que corre es muy importante, y es evaluado de UNA de estas maneras:

> ***Global Code***  El *enviroment* por defecto en el que tu código es ejecutado por primera vez.

> ***Function Code*** Cuando el flujo de ejecución entra en el cuerpo de una función.

> *(...)*

> *(...)*, entonces, pensemos en el termino *execution context* como el *enviroment*/***scope*** en el que el actual código está siendo evaluado.

En otras palabras, cuando corremos el programa, empieza en el ***Global Execution Context***. Algunas variables son declaradas dentro del **Global Execution Context**. A estas las llamamos *Global Variables*. Cuando el programa llama a una función, ¿qué pasa? Unos simples pasos:

1. JavaScript crea un nuevo *execution context*, un *local execution context*
2. Ese *local execution context* tendrá su propio set de variables, que serán locales a ese contexto de ejecución.
3. El nuevo *execution context* es jalado hacia el *execution stack*. Piensa en el *execution stack* como un mecanismo del programa para saber en qué punto de la ejecución se encuentra.

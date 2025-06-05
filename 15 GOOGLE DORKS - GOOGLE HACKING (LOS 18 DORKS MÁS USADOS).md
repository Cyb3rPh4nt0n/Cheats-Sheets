El 'Google Dork' es una técnica de búsqueda avanzada que utiliza operadores y palabras clave específicas en el buscador de Google para encontrar información que normalmente no aparece en los resultados de búsqueda regulares.
La técnica de 'Google Dorking' se utiliza a menudo en el hacking para encontrar información sensible y crítica en línea. Es una forma eficaz de recopilar información valiosa de una organización o individuo que puede ser utilizada para realizar pruebas de penetración y otros fines de seguridad.
Al utilizar Google Dorks, un atacante puede buscar información como nombres de usuarios y contraseñas, archivos confidenciales, información de bases de datos, números de tarjetas de crédito y otra información crítica. También pueden utilizar esta técnica para identificar vulnerabilidades en aplicaciones web, sitios web y otros sistemas en línea.
Es importante tener en cuenta que la técnica de Google Dorking no es ilegal en sí misma, pero puede ser utilizada con fines maliciosos. Por lo tanto, es crucial utilizar esta técnica con responsabilidad y ética en el contexto de la seguridad informática y el hacking ético.
## Google Dork Cheat Sheet:

| FILTRO                                  | DESCRIPCIÓN                                                                                                                | EJEMPLO                                             |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| allintext                               | Busca todas las palabras clave indicadas.                                                                                  | allintext:"keyword"                                 |
| intext                                  | Busca las apariciones de palabras clave todas a la vez o de una en una.                                                    | intext:"keyword"                                    |
| inurl                                   | Busca una URL que coincida con una de las palabras clave.                                                                  | inurl:"keyword"                                     |
| allinurl                                | Busca una URL que coincida con todas las palabras clave de la consulta.                                                    | allinurl:"keyword"                                  |
| intitle                                 | Busca apariciones de palabras clave en el título todos o uno.                                                              | intitle:"keyword"                                   |
| allintitle                              | Busca apariciones de palabras clave de una sola vez.                                                                       | allintitle:"keyword"                                |
| site                                    | Busca específicamente en ese sitio concreto y enumera todos los resultados de ese sitio.                                   | site:"www.google.com"                               |
| filetype                                | Busca un tipo de archivo concreto mencionado en la consulta.                                                               | filetype:"pdf"                                      |
| link                                    | Busca enlaces externos a páginas.                                                                                          | link:"keyword"                                      |
| numrange                                | Sirve para localizar números concretos en sus búsquedas.                                                                   | numrange:321-325                                    |
| before/after                            | Permite buscar dentro de un intervalo de fechas determinado.                                                               | filetype:pdf & (before:2000-01-01 after:2001-01-01) |
| allinanchor (and also inanchor)         | Muestra los sitios que tienen los términos clave en los enlaces que apuntan a ellos, por orden de mayor número de enlaces. | inanchor:rat                                        |
| allinpostauthor (and also inpostauthor) | Exclusivo de la búsqueda de blogs, selecciona las entradas escritas por personas concretas.                                | allinpostauthor:"keyword"                           |
| related                                 | Lista las páginas web que son «similares» a una página web especificada.                                                   | related:www.google.com                              |
| cache                                   | Muestra la versión de la página web que Google tiene en su caché.                                                          | cache:www.google.com                                |
## Operadores:
### Search Term
Este operador sólo busca la frase exacta entre comillas. Es ideal cuando la frase que busca es ambigua y puede confundirse fácilmente con otra, o cuando no obtiene resultados suficientemente relevantes. 
Por ejemplo: "Tinned Sandwiches"
### OR
Este operador autoexplicativo busca un término de búsqueda dado O un término equivalente. 
site:facebook.com | site:twitter.com
### AND
Este operador autoexplicativo busca un término de búsqueda dado Y otro término dado. 
site:facebook.com & site:twitter.com
### Combinaciones de Operadores
(site:facebook.com | site:twitter.com) & intext:"login"
(site:facebook.com | site:twitter.com)  (intext:"login")
### Incluir Resultados
Esto ordenará los resultados por el número de apariciones de la palabra clave.
-site:facebook.com +size:facebook.*
### Excluir Resultados
Esto excluirá los resultados a través de una palabra clave.
site:facebook.* -site:facebook.com
### Sinónimos
Si añades una virgulilla (~) a una palabra de búsqueda, le indicas a Google que quieres que te muestre también sinónimos de ese término. Por ejemplo, si escribes «~configurar», aparecerán resultados que incluyen palabras como «configurar», «recopilar» y «cambiar», que son sinónimos de «configurar». Dato curioso: «set» es la palabra con más definiciones del diccionario.
~set
### Patrón Global (`*`)
Poner un asterisco en una búsqueda le dice a Google 'no sé qué va aquí'. Básicamente, es muy bueno para encontrar letras de canciones o nombres de cosas medio recordados.
site:`*`.com
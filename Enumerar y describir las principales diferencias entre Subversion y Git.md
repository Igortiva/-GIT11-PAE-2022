# Enumerar y describir las principales diferencias entre Subversion y Git
_La diferencia fundamental entre Subversion y Git es que el primero es centralizado y el segundo, distribuido_
Los sistemas centralizados como Subversion disponen de un servidor donde están los archivos de todo el proyecto, junto con todas las modificaciones. Los desarrolladores necesitan descargar del servidor central aquellos archivos o partes del proyecto que desean modificar, y necesitan estar conectados a la red cuando se requiere enviar cambios en el código, como hemos explicado antes.

Por el contrario, los sistemas distribuidos como Git disponen de una copia local completa del repositorio, para cada desarrollador que participa en el proyecto. En los sistemas distribuidos no es necesaria la conexión a la red cuando se requiere hacer confirmaciones (commit), solamente cuando se necesita sincronizar el repositorio local contra el repositorio remoto.

Git también facilita el funcionamiento de los proyectos en local, ya que cada desarrollador tiene una copia del mismo y no solamente el conjunto de archivos con los que está trabajando. Esta diferencia fundamental a hecho posible el éxito de Git en el panorama actual, ya que permite que los desarrolladores trabajen de manera remota con mayor facilidad, incluso sin conexión a la red local o Internet.

Entre los equipos técnicos, Subversión se conoce muy habitualmente como  SVN, el comando que se usa para trabajar con el sistema.

## _¿Cuáles son las diferencias entre Subversion y Git?_
Los repositorios de Subversion (SVN) son similares a los repositorios de Git, pero hay diferencias cuando se refiere a la arquitectura de tus proyectos.

# Estructura de directorios
Cada referencia, o instantánea etiquetada de una confirmación, en un proyecto está organizada en subdirectorios específicos, como trunk, branches y tags. Por ejemplo, un proyecto SVN con dos características bajo desarrollo debería parecerse a esto:

 > sample_project/trunk/README.md
 > sample_project/trunk/lib/widget.rb
 > sample_project/branches/new_feature/README.md
 > sample_project/branches/new_feature/lib/widget.rb
 > sample_project/branches/another_new_feature/README.md
 > sample_project/branches/another_new_feature/lib/widget.rb
 
## Un flujo de trabajo SVN se parece a esto:

El directorio trunk representa la versión estable más reciente de un proyecto.
El trabajo de características activas se desarrolla dentro de subdirectorios en branches.
Una vez finalizada una característica, el directorio de características se combina y trunk se elimina.
Los proyectos de Git también se almacenan dentro de un directorio único. Pero Git oculta los detalles de sus referencias almacenándolos en un directorio .git especial. Por ejemplo, un proyecto Git con dos características bajo desarrollo debería parecerse a esto:

>  sample_project/.git
>  sample_project/README.md
>  sample_project/lib/widget.rb

## Un flujo de trabajo Git se parece a esto:

Un repositorio Git almacena el historial completo de todas sus ramas y etiquetas en el directorio .git.
El último lanzamiento estables se contiene dentro de la rama predeterminada.
El trabajo de característica activa se desarrolla en ramas separadas.
Cuando una característica finaliza, la rama de característica se fusiona en la rama predeterminada y se borra.
A diferencia de SVN, con Git la estructura del directorio permanece igual, pero los contenidos de los archivos cambia en base a tu rama.

# Incluir los subproyectos
Un subproyecto es un proyecto que se desarrolla y administra fuera de tu proyecto principal. Normalmente importas un subproyecto para agregar alguna funcionalidad a tu proyecto sin necesidad de mantener el código. Cada vez que el proyecto se actualiza, puedes sincronizarlo con tu proyecto para garantizar que todo esté actualizado.

En SVN, un subproyecto se denomina SVN externo. En Git, se denomina submódulo de Git. A pesar de que conceptualmente son similares, los submódulos Git no se mantienen actualizados de forma automática; debes solicitar explícitamente que se traiga una nueva versión a tu proyecto.

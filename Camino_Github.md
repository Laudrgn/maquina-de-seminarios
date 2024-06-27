Primero hay que hacer el repositorio en GitHub por web si va a ser nuestro propio repositorio
Con un archivo vacío, ejemplo el readme.md

O ir a algún repositorio que quiero probar/trabajar

copiar la URL del proyecto desde el botón CODE

SOLO COPIAR Repositorio: (si queres hacer push, ver más abajo)

Luego clonarlo en local:

Ubicarse por línea de comandos en la carpeta donde se va a clonar el repositorio
Nota: Al clonar se crea una nueva carpeta con el nombre del repositorio que le dimos en Github

$git clone https://github.com/USUARIO/NOMBREDELREPO.git
Username: TU_USUARIO
Password: TU_TOKEN

Nota: ver creación de tokens más abajo

con $cd NOMBREDELREPO entramos en la carpeta.

Clonar ya poniendo nombre de carpeta DIFERENTE del que viene como nombre de repo:
$git clone https://github.com/USUARIO/NOMBREDELREPO.git NOMBREDECARPETANUEVO


Ya podemos trabajar.

Creamos un archivo vacío
Ej en la línea de comandos 
$touch archivotest.md

Ahora lo agregamos a la zona de stage: indico cuales archivos fueron modificados y quiero que aparezcan en el repo de Github

$git add NOMBREDELARCHIVO

en este ejemplo: 
$git add archivotest.md

Podemos seguir agregando más archivos de la misma manera, o añadir todos con 
$git add --all.      
importante agregar el punto al final! OJO que sube todo, aun cosas que no necesitaríamos subir!

podemos verificar cuales archivos ya fueron añadidos al stage con
$git status

Una vez que estén listos, los podemos agregar al repo con 
$git commit -m "mensaje"
Donde mensaje lo cambio por algo descriptivo del porqué de estos cambios
por ej:
$git commit -m "primer commit"

Puedo chequear por github web al repositorio correspondiente si se subieron/modificaron los archivos correspondientes

-------------------
SOY DUEÑO O COLAB del Repo y quiero hacer PUSH
Colocar tu nombre de usuario @ github

$git clone https://TUUSUARIO@github.com/USUARIO/NOMBREDELREPO.git NOMBREDECARPETANUEVO

Y luego al hacer push, te va a pedir una contraseña, que es el token personal! Ver autenticaciones abajo

--------------------
Autenticaciones:
Para cambiar archivos en mi propio repositorio, debo crear un token personal
En la web, ir a settings -> developer settings -> personal access tokens -> classic token -> generate new token
colocar un nombre descriptivo, un término de expiración (30 días por ej) y darles permisos de "repo" para poder acceder

copiar el token - es una línea de códigos

En caso que no te deje acceder más a tus proyectos porque se venció el token:
con 
$git remote -v 
vemos los repositorios vinculados
$git remote remove origin 
los borramos (chequeamos con $git remote -v y no habría nada)
Volvemos a colocarlos con nuestro token
$git remote add origin https://TOKEN@github.com/USUARIO/REPO.git


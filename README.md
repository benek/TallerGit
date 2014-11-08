Taller de Git
=============


Javier Alberto Ramírez Hernández  
<benek@javamexico.org>  
www.SintelTI.mx  

Introducción
------------

* **Control de Versiones**

    Ventajas: revertir, comparar, revisar... intercambiar.  
    Tener la seguridad de poder recuperar tu trabajo en caso extremo, y que sea fácil.
    Poder revisar la historia de un proyecto.
* **Git vs Otros**

    Versionamiento en el "cretácico":
    ![](http://img18.imageshack.us/img18/7883/capturadepantalla201205q.png)  
  
    Después, versionamiento en equipo local (patches):  

    ![](http://git-scm.com/figures/18333fig0101-tn.png)  
  
    Control de Versiones Centralizado (CVS, Subversion):  
  
    ![](http://git-scm.com/figures/18333fig0102-tn.png)  
  
    Control de Versiones Distribuido (Git, Mercurial, Bazaar):  
  
    ![](http://git-scm.com/figures/18333fig0103-tn.png)  

* **Integridad**

    En su mayoría, cada una de las operaciones de Git se realizan localmente.
    Para cada commit, Git asigna como identificador un checksum SHA-1. Ejemplo: 24b9da6552252987aa493b52f8696cd6d3b00373. No un número incremental como en otros sistemas de control de versiones como CVS o Subversion.
    Casi todas las operaciones en Git resultan en la 'adición' de información al índice, aunque estemos 'eliminando' o 'modificando'.
    Los tres estados (de la materia Git):
    ![](http://git-scm.com/figures/18333fig0106-tn.png)  

* **Configuración básica de Git**  

    git config

		git config --global user.name "Tu Nombre"
		git config --global user.email "xbenek@gmail.com"

Git 101
-------
  
**git init**

* Inicializa un nuevo repositorio de Git
* Crea una carpeta oculta llamada ‘.git’, ésta contiene el “índice" y todo cambio en el repositorio

**git clone [url]**

* Obtiene un repositorio remoto a tu equipo local, con todo su historial.
		
**Ciclo de vida de los archivos en Git:**

![](http://git-scm.com/figures/18333fig0201-tn.png)

**git status**

* Tu mejor amigo
* Nos indica el estado del repositorio, si ha tenido cambios o no, y si hay cambios nos indica el estado de los mismos

**git add <path>**

* Añade un archivo, carpeta o ruta a la *staging area*, que es la zona donde se acumula lo que está por guardarse. Estos cambios aún no están en el repositorio. Podemos añadir o remover cosas del *stage* antes de realizar un *commit*.

**git commit**

* Guarda los cambios en el repositorio de lo que hayamos añadido previamente al *stage*. Opcionalmente añadiremos un mensaje para describir el cambio con la opción -m y un mensaje entre comillas.

**Ignorando archivos o directorios**

* Por convención Git buscará dentro del repositorio un archivo con nombre '.gitignore', en el cuál podemos indicar expresiones de rutas o archivos para que Git no los tome en cuenta.
* Si necesitamos que estas reglas estén disponibles para todas las personas que vean el repositorio necesitaremos agregar el archivo .gitignore a un commit.
* Github tiene un repositorio con archivos .gitignore de ejemplo para muchos escenarios, disponible en: [https://github.com/github/gitignore](https://github.com/github/gitignore)
* Y también un archivo con configuraciones comunes: [https://gist.github.com/octocat/9257657](https://gist.github.com/octocat/9257657)

**git log**

* Revisa el historial de commits del repositorio y su información detallada.
* Una muy buena alternativa para visualizar el log es: [http://fredkschott.com/post/2014/02/git-log-is-so-2005/](http://fredkschott.com/post/2014/02/git-log-is-so-2005/)

**Ignorando cambios en archivos que son parte del índice**

	git update-index --assume-unchanged path/to/file.txt
	git update-index --no-assume-unchanged path/to/file.txt

**git reset**

* Quita archivos del *stage* y por consecuencia no serán parte del siguiente commit.

**git show**
* Muestra la información a detalle de un commit, incluyendo los cambios realizados.

**git diff**

* Compara los cambios entre versiones, que puede ser un commit pasado o el apuntador al último commit “HEAD”, o comparar con un branch.

**git checkout -- <target>**

* Deshace los cambios de un archivo que está en el stage, para que regrese al mismo estado que en el último commit.

**Eliminar y mover archivos**

* **git rm**
* **git mv**
* **--cached**

**Deshaciendo cosas**

* Con *git commit --amend* podemos añadir al último commit realizado algún archivo que hayamos olvidado, o corregir el mensaje del commit.
* *git reset*
* *git checkout*
* *git revert <commit>* revierte los cambios hechos por un commit previo y registra estos cambios en un nuevo commit. 

**git remote**

* Añade un repositorio remoto para poder obtener o enviar cambios

**git pull**

* “Jala” los commits que existan en un repositorio remoto (y que estén en nuestro repositorio local) hacia nuestra copia.

**git push**

* *Empuja* commits hacia un repositorio remoto. Cuando es la primera vez podemos ejecutar este comando añadiendo “-u origin master”, el comando -u hace que git recuerde los parámetros.

**Tags**
* git tag -a v1.4 -m 'Versión 1.4'

**Branches**

* Un branch es una ramificación de la línea de desarrollo central (branch master), es decir, es una nueva línea de desarrollo en la cuál pueden implementarse cambios o nuevas ideas sin afectar la línea base, con el fin de que estos cambios puedan ser integrados al branch master cuando su funcionamiento ya esté garantizado o descartados si simplemente se trató de una mala idea.

* La mayoría de los sistemas de control de versiones cuentan con la característica de branching, aunque en su mayoría resultan ser de implementación dolorosa ya que algunos implementan el branching copiando todo el estado actual de la rama base, esto hace que la integración (merge) también sea muy dolorosa e ineficaz. Git se diferencía de los demás sistemas de control de versiones porque el branching en Git es bastante liviano, y toma en cuenta (como todo en Git) solamente los datos que varían, no los que no han cambiado. Esto hace que el proceso de crear un branch en Git sea inmediato, y el merge sea muy breve también.

**Branching y Merging**

	git branch
	git branch <nombrebranch>
	git checkout <nombrebranch>
	git checkout -b <nombrebranch>
	git merge <nombrebranch>

**git stash**

* Funciona como un guardado rápido provisional, ya sea para cambiar de rama o para hacer pull sobre cambios que generarían un conflicto en los archivos locales que hemos modificado pero no hemos confirmado mediante un *commit*.

**Resolución de conflictos**

* Cuando el algoritmo de *merge* de Git no puede integrar cambios provenientes de dos fuentes, es probable que nos deje a nosotros la tarea de realizar esta integración de manera manual.

**git rebase**

* Sirve para reescribir la historia de commits del repositorio, este comando literalmente regresa el estado desde donde le hayamos indicado y vuelve a efectuar los commits con los cambios que le hayamos ordenado. Al reescribir la historia tenemos la opción de descartar commits, fusionarlos o editarlos.

		git rebase -i HEAD~3


=============

Este taller está basado en el libro Pro Git, de Scott Chacon.
[Creative Commons Attribution Non Commercial Share Alike 3.0 license](http://creativecommons.org/licenses/by-nc-sa/3.0/)

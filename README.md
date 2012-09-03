Taller de Git
=============


Javier Alberto Ramírez Hernández  
<benek@javamexico.org>  
www.SintelTI.mx  

Introducción
------------

* **Control de Versiones**

    Ventajas: revertir, comparar, revisar... intercambiar.  
    Tener la seguridad de poder recuperar tu trabajo si metes la pata, y que sea fácil.  
* **Historia**
* **Git vs Otros**

    Versionamiento en el cretácico:  
    ![](http://img18.imageshack.us/img18/7883/capturadepantalla201205q.png)  
  
    Después, versionamiento en equipo local (patches):  

    ![](http://git-scm.com/figures/18333fig0101-tn.png)  
  
    Control de Versiones Centralizado (CVS, SVN):  
  
    ![](http://git-scm.com/figures/18333fig0102-tn.png)  
  
    Control de Versiones Distribuido (Git, Mercurial, Bazaar):  
  
    ![](http://git-scm.com/figures/18333fig0103-tn.png)  

* **Premisas**

    En su mayoría, cada una de las operaciones de Git se realizan localmente.  
    Integridad (24b9da6552252987aa493b52f8696cd6d3b00373).  
    Casi en todas las operaciones que hace Git solamente agrega 'datos'.  
    Los tres estados (de la materia Git):  
    ![](http://git-scm.com/figures/18333fig0106-tn.png)  

* **Configuración básica de Git**  

    git config  

Git 101
-------

* **Obtener un repositorio**
    - git init  
    - git clone [url]  
* **Operaciones con archivos**
    - Ciclo de vida de los archivos:  
        ![](http://git-scm.com/figures/18333fig0201-tn.png)
    - git status
    - Agregar nuevos archivos al repo
    - Añadir archivos modificados a un commit
    - Ignorar archivos o directorios
    - git diff
    - git commit
    - Saltando la 'staging area'
    - Eliminar y mover archivos
* **Historial de cambios**
* **Recuperando después de una metida de pata (undoing things)**
    - --amend
    - reset
    - checkout
    - revert
* **Repositorios remotos**
* **Tags**
* **Tips & tricks**
    - Autocompletado en la shell (bash)
    - Alias para comandos

Git Branches
------------

* **¿Qué es un branch?**
    - Un branch es una ramificación de la línea de desarrollo central (branch master), es decir, es una nueva línea de desarrollo en la cuál pueden implementarse cambios o nuevas ideas sin afectar la línea base, con el fin de que estos cambios puedan ser integrados al branch master cuando su funcionamiento ya esté garantizado o descartados si simplemente se trató de una mala idea.
    - La mayoría de los sistemas de control de versiones cuentan con la característica de branching, aunque en su mayoría resultan ser de implementación dolorosa ya que algunos implementan el branching copiando todo el estado actual de la rama base, esto hace que la integración (merge) también sea muy dolorosa e ineficaz. Git se diferencía de los demás sistemas de control de versiones porque el branching en Git es bastante liviano, y toma en cuenta (como todo en Git) solamente los datos que varían, no los que no han cambiado. Esto hace que el proceso de crear un branch en Git sea inmediato, y el merge sea muy breve también.
* **Branching y Merging**
    - git branch
    - git branch <nombrebranch>
    - git checkout <nombrebranch>
    - git checkout -b <nombrebranch>
    - git merge <nombrebranch>
* **Resolución de conflictos y avances sin commit
* **Branches remotos**
    - Pushing & pulling de branches remotos

Git Tools
---------

* **Stashing**
* **Rebase**

=============

Este taller está basado en el libro Pro Git, de Scott Chacon.  
[Creative Commons Attribution Non Commercial Share Alike 3.0 license](http://creativecommons.org/licenses/by-nc-sa/3.0/)

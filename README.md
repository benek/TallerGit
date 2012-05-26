Taller de Git
=============

Javier Alberto Ramírez Hernández  
<xbenek@dev.java.net>  
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
* **Branching y Merging**
* **Branches remotos**

Git Tools
---------

* **Stashing**
* **Rebase**

Github.com
----------

* **¿Qué es?**
* **...**


=============

Este taller está basado en el libro Pro Git, de Scott Chacon.  
[Creative Commons Attribution Non Commercial Share Alike 3.0 license](http://creativecommons.org/licenses/by-nc-sa/3.0/)

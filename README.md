## Ejercicios de creación y actualización de repositorios

### Ejercicio 1

Configurar Git definiendo el nombre del usuario, el correo electrónico y activar el coloreado de la salida. 

Mostrar la configuración final.

```bash
williamgalvis@WilliamalvisAir testGit % git config --global user.email 35779309+wicho120@users.noreply.github.com
williamgalvis@WilliamalvisAir testGit % git config --global user.name Wicho120
```

### Ejercicio 2

Crear un repositorio nuevo con el nombre libro y mostrar su contenido.

```bash
williamgalvis@WilliamalvisAir libro % git init
Initialized empty Git repository in /Users/williamgalvis/Desktop/libro/.git/
```

### Ejercicio 3

Comprobar el estado del repositorio.

Crear un fichero `indice.txt` con el siguiente contenido:

```
Capítulo 1: Introducción a Git
Capítulo 2: Flujo de trabajo básico
Capítulo 3: Repositorios remotos
```

Comprobar de nuevo el estado del repositorio.

Añadir el fichero a la zona de intercambio temporal.

Volver a comprobar una vez más el estado del repositorio.

```bash
williamgalvis@WilliamalvisAir libro % git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        indice.txt

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % git add indice.txt 
williamgalvis@WilliamalvisAir libro % git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   indice.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 4

Realizar un commit de los últimos cambios con el mensaje “Añadido índice del libro.” y ver el estado del repositorio.

```bash
williamgalvis@WilliamalvisAir libro % git commit -m "Añadido indice del libro"
[main (root-commit) ff812a7] Añadido indice del libro
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 indice.txt
williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 5

Cambiar el fichero `indice.txt` para que contenga lo siguiente:

```
Capítulo 1: Introducción a Git
Capítulo 2: Flujo de trabajo básico
Capítulo 3: Gestión de ramas
Capítulo 4: Repositorios remotos
```

Mostrar los cambios con respecto a la última versión guardada en el repositorio.

Hacer un commit de los cambios con el mensaje “*Añadido capítulo 3 sobre gestión de ramas*”.

```
williamgalvis@WilliamalvisAir libro % git diff 67be86d9d605d00a374219967f18281de4cf7ded
diff --git a/indice.txt b/indice.txt
index 8142b7e..3c4c2a7 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,3 +1,4 @@
 Capítulo 1: Introducción a Git
 Capítulo 2: Flujo de trabajo básico
-Capítulo 3: Repositorios remotos
\ No newline at end of file
+Capítulo 3: Gestión de ramas
+Capítulo 4: Repositorios remotos
\ No newline at end of file
williamgalvis@WilliamalvisAir libro % git add indice.txt 
williamgalvis@WilliamalvisAir libro % git commit -m "Añadido capitulo 3 sobre gestion de ramas"
[main a0f91a6] Añadido capitulo 3 sobre gestion de ramas
 1 file changed, 2 insertions(+), 1 deletion(-)
williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 6

Mostrar los cambios de la última versión del repositorio con respecto a la anterior.

Cambiar el mensaje del último commit por “*Añadido capítulo 3 sobre gestión de ramas al índice.*”

Volver a mostrar los últimos cambios del repositorio.

```bash
williamgalvis@WilliamalvisAir libro % git commit --amend -m "Añadido capítulo 3 sobre gestión de ramas al índice."
[main 1e8e28c] Añadido capítulo 3 sobre gestión de ramas al índice.
 Date: Tue Sep 17 11:16:55 2024 -0500
 1 file changed, 2 insertions(+), 1 deletion(-)
williamgalvis@WilliamalvisAir libro % git log --oneline                                                           
1e8e28c (HEAD -> main) Añadido capítulo 3 sobre gestión de ramas al índice.
67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % git log          
commit 1e8e28cf9e6c8d9d6055344cea2942b654b0a0d6 (HEAD -> main)
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:16:55 2024 -0500

    Añadido capítulo 3 sobre gestión de ramas al índice.

commit 67be86d9d605d00a374219967f18281de4cf7ded
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:15:30 2024 -0500

    Añadido indice del libro
williamgalvis@WilliamalvisAir libro % 
```





## Ejercicios de manejo del historial de cambios

### Ejercicio 1

Mostrar el historial de cambios del repositorio.

Crear la carpeta capitulos y crear dentro de ella el fichero capitulo1.txt con el siguiente texto.

```
Git es un sistema de control de versiones ideado por Linus Torvalds.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje *“Añadido capítulo 1.”* Volver a mostrar el historial de cambios del repositorio.

```
williamgalvis@WilliamalvisAir libro % git log
commit 1e8e28cf9e6c8d9d6055344cea2942b654b0a0d6 (HEAD -> main)
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:16:55 2024 -0500

    Añadido capítulo 3 sobre gestión de ramas al índice.

commit 67be86d9d605d00a374219967f18281de4cf7ded
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:15:30 2024 -0500

    Añadido indice del libro
williamgalvis@WilliamalvisAir libro % git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md
        capitulos/

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % git add capitulos/capitulo1.txt 
williamgalvis@WilliamalvisAir libro % git commit -m "Añadido capítulo 1."
[main 9c60efa] Añadido capítulo 1.
 1 file changed, 1 insertion(+)
 create mode 100644 capitulos/capitulo1.txt
williamgalvis@WilliamalvisAir libro % git log --oneline
9c60efa (HEAD -> main) Añadido capítulo 1.
1e8e28c Añadido capítulo 3 sobre gestión de ramas al índice.
67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % 
```



### Ejercicio 2

Crear el fichero `capitulo2.txt` en la carpeta capitulos con el siguiente texto.

```
El flujo de trabajo básico con Git consiste en: 1- Hacer cambios en el repositorio. 2- Añadir los cambios a la zona de intercambio temporal. 3- Hacer un commit de los cambios.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje “*Añadido capítulo 2.”*

Mostrar las diferencias entre la última versión y dos versiones anteriores.

```bash
williamgalvis@WilliamalvisAir libro % git add capitulos/capitulo2.txt 
williamgalvis@WilliamalvisAir libro % git commit -m "Añadido capítulo 2."
[main 16e5caa] Añadido capítulo 2.
 1 file changed, 1 insertion(+)
 create mode 100644 capitulos/capitulo2.txt
williamgalvis@WilliamalvisAir libro % git diff 16e5caab 1e8e28cf
diff --git a/capitulos/capitulo1.txt b/capitulos/capitulo1.txt
deleted file mode 100644
index f4068a7..0000000
--- a/capitulos/capitulo1.txt
+++ /dev/null
@@ -1 +0,0 @@
-Git es un sistema de control de versiones ideado por Linus Torvalds.
\ No newline at end of file
diff --git a/capitulos/capitulo2.txt b/capitulos/capitulo2.txt
deleted file mode 100644
index aeb3f33..0000000
--- a/capitulos/capitulo2.txt
+++ /dev/null
@@ -1 +0,0 @@
-El flujo de trabajo básico con Git consiste en: 1- Hacer cambios en el repositorio. 2- Añadir los cambios a la zona de intercambio temporal. 3- Hacer un commit de los cambios.
\ No newline at end of file		
```

### Ejercicio 3

Crear el fichero capitulo3.txt en la carpeta capitulos con el siguiente texto.

```
Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje *“Añadido capítulo 3.”*

Mostrar las diferencias entre la primera y la última versión del repositorio.

```bash
williamgalvis@WilliamalvisAir libro % git add capitulos/capitulo3.txt 
williamgalvis@WilliamalvisAir libro % git commit -m "Añadido capitulo 3."
[main a793a1d] Añadido capitulo 3.
 1 file changed, 1 insertion(+)
 create mode 100644 capitulos/capitulo3.txt
williamgalvis@WilliamalvisAir libro % git diff a793a1d8 67be86d9 
diff --git a/capitulos/capitulo1.txt b/capitulos/capitulo1.txt
deleted file mode 100644
index f4068a7..0000000
--- a/capitulos/capitulo1.txt
+++ /dev/null
@@ -1 +0,0 @@
-Git es un sistema de control de versiones ideado por Linus Torvalds.
\ No newline at end of file
diff --git a/capitulos/capitulo2.txt b/capitulos/capitulo2.txt
deleted file mode 100644
index aeb3f33..0000000
--- a/capitulos/capitulo2.txt
+++ /dev/null
@@ -1 +0,0 @@
-El flujo de trabajo básico con Git consiste en: 1- Hacer cambios en el repositorio. 2- Añadir los cambios a la zona de intercambio temporal. 3- Hacer un commit de los cambios.
r un commit de los cambios.
\ No newline at end of file
diff --git a/capitulos/capitulo3.txt b/capitulos/capitulo3.txt
deleted file mode 100644
index 534b9a9..0000000
--- a/capitulos/capitulo3.txt
+++ /dev/null
@@ -1 +0,0 @@
-Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.
\ No newline at end of file
diff --git a/indice.txt b/indice.txt
index 3c4c2a7..8142b7e 100644
--- a/indice.txt
+++ b/indice.txt
@@ -1,4 +1,3 @@
 Capítulo 1: Introducción a Git
 Capítulo 2: Flujo de trabajo básico
-Capítulo 3: Gestión de ramas
-Capítulo 4: Repositorios remotos
\ No newline at end of file
+Capítulo 3: Repositorios remotos
\ No newline at end of file
(END)
```

### Ejercicio 4

Añadir al final del fichero `indice.txt` la siguiente línea:

```
Capítulo 5: Conceptos avanzados
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit de los cambios con el mensaje “Añadido capítulo 5 al índice.”.

Mostrar quién ha hecho cambios sobre el fichero `indice.txt`.

```bash
williamgalvis@WilliamalvisAir libro % git add indice.txt 
williamgalvis@WilliamalvisAir libro % git commit -m "Añadido capítulo 5 al índice."
[main cac76e2] Añadido capítulo 5 al índice.
 1 file changed, 2 insertions(+), 1 deletion(-)
williamgalvis@WilliamalvisAir libro % git log indice.txt 
commit cac76e238df3836e5fc9edd85a57e31cad2dc00d (HEAD -> main)
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:32:38 2024 -0500

    Añadido capítulo 5 al índice.

commit 1e8e28cf9e6c8d9d6055344cea2942b654b0a0d6
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:16:55 2024 -0500

    Añadido capítulo 3 sobre gestión de ramas al índice.

commit 67be86d9d605d00a374219967f18281de4cf7ded
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:15:30 2024 -0500

    Añadido indice del libro
```





## Ejercicios de deshacer cambios

### Ejercicio 1

Eliminar la última línea del fichero `indice.txt` y guardarlo.

Comprobar el estado del repositorio.

Deshacer los cambios realizados en el fichero `indice.txt` para volver a la versión anterior del fichero.

Volver a comprobar el estado del repositorio.

```bash
williamgalvis@WilliamalvisAir libro % git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   indice.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

no changes added to commit (use "git add" and/or "git commit -a")
williamgalvis@WilliamalvisAir libro % git checkout indice.txt 
Updated 1 path from the index
williamgalvis@WilliamalvisAir libro % git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 2

Eliminar la última línea del fichero `indice.txt` y guardarlo.

Añadir los cambios a la zona de intercambio temporal.

Comprobar de nuevo el estado del repositorio.

Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.

Comprobar de nuevo el estado del repositorio.

Deshacer los cambios realizados en el fichero `indice.txt` para volver a la versión anterior del fichero.

Volver a comprobar el estado del repositorio.

```
williamgalvis@WilliamalvisAir libro % git add indice.txt 
williamgalvis@WilliamalvisAir libro % git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   indice.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

williamgalvis@WilliamalvisAir libro % git  restore --staged indice.txt 
williamgalvis@WilliamalvisAir libro % git status                      
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   indice.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

no changes added to commit (use "git add" and/or "git commit -a")
williamgalvis@WilliamalvisAir libro % git checkout indice.txt 
Updated 1 path from the index
williamgalvis@WilliamalvisAir libro % git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 3

Eliminar la última línea del fichero `indice.txt` y guardarlo.

Eliminar el fichero `capitulos/capitulo3.txt`.

Añadir un fichero nuevo `capitulos/capitulo4.txt` vacío.

Añadir los cambios a la zona de intercambio temporal.

Comprobar de nuevo el estado del repositorio.

Quitar los cambios de la zona de intercambio temporal, pero mantenerlos en el directorio de trabajo.

Comprobar de nuevo el estado del repositorio.

Deshacer los cambios realizados para volver a la versión del repositorio.

Volver a comprobar el estado del repositorio.

```bash
williamgalvis@WilliamalvisAir libro % git status
On branch main
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    capitulos/capitulo3.txt
        modified:   indice.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md
        capitulos/capitulo4.txt

no changes added to commit (use "git add" and/or "git commit -a")
williamgalvis@WilliamalvisAir libro % git add indice.txt 
williamgalvis@WilliamalvisAir libro % git add capitulos/capitulo3.txt
williamgalvis@WilliamalvisAir libro % git add capitulos/capitulo4.txt 
williamgalvis@WilliamalvisAir libro % git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    capitulos/capitulo3.txt
        new file:   capitulos/capitulo4.txt
        modified:   indice.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

williamgalvis@WilliamalvisAir libro % git restore --staged capitulos/capitulo3.txt indice.txt capitulos/capitulo4.txt 
williamgalvis@WilliamalvisAir libro % git status
On branch main
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    capitulos/capitulo3.txt
        modified:   indice.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md
        capitulos/capitulo4.txt

no changes added to commit (use "git add" and/or "git commit -a")
williamgalvis@WilliamalvisAir libro % git restore capitulos/capitulo3.txt indice.txt capitulos/capitulo4.txt 
error: pathspec 'capitulos/capitulo4.txt' did not match any file(s) known to git
williamgalvis@WilliamalvisAir libro % git restore capitulos/capitulo3.txt indice.txt                        
williamgalvis@WilliamalvisAir libro % git status 
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % 
```



### Ejercicio 4

Eliminar la última línea del fichero `indice.txt` y guardarlo.

Eliminar el fichero `capitulos/capitulo3.txt`.

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “*Borrado accidental.*”

Comprobar el historial del repositorio.

Deshacer el último commit pero mantener los cambios anteriores en el directorio de trabajo y la zona de intercambio temporal.

Comprobar el historial y el estado del repositorio.

Volver a hacer el commit con el mismo mensaje de antes.

Deshacer el último commit y los cambios anteriores del directorio de trabajo volviendo a la versión anterior del repositorio.

Comprobar de nuevo el historial y el estado del repositorio.

```
williamgalvis@WilliamalvisAir libro % git add indice.txt capitulos/capitulo3.txt
williamgalvis@WilliamalvisAir libro % git commit -m "Borrado accidental"
[main 5997190] Borrado accidental
 2 files changed, 1 insertion(+), 3 deletions(-)
 delete mode 100644 capitulos/capitulo3.txt
williamgalvis@WilliamalvisAir libro % git log
commit 599719001dd6df9c9243be60911c03101283439b (HEAD -> main)
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:50:17 2024 -0500

    Borrado accidental

commit cac76e238df3836e5fc9edd85a57e31cad2dc00d
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:32:38 2024 -0500

    Añadido capítulo 5 al índice.

commit a793a1d8a811b000246282e332e2f9cf5cb0ca29
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:29:59 2024 -0500

    Añadido capitulo 3.

commit 16e5caab0b2a2981837c4cc65370d4dff4fa4d4f
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:27:17 2024 -0500

    Añadido capítulo 2.

commit 9c60efa371975164a9a56a2186a2374e3dae9014
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:24:40 2024 -0500

    Añadido capítulo 1.

commit 1e8e28cf9e6c8d9d6055344cea2942b654b0a0d6
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:16:55 2024 -0500

    Añadido capítulo 3 sobre gestión de ramas al índice.

commit 67be86d9d605d00a374219967f18281de4cf7ded
Author: Wicho120 <35779309+wicho120@users.noreply.github.com>
Date:   Tue Sep 17 11:15:30 2024 -0500

    Añadido indice del libro
williamgalvis@WilliamalvisAir libro % git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % git revert HEAD --no-edit
[main 00cb66a] Revert "Borrado accidental"
 Date: Tue Sep 17 11:52:38 2024 -0500
 2 files changed, 3 insertions(+), 1 deletion(-)
 create mode 100644 capitulos/capitulo3.txt
williamgalvis@WilliamalvisAir libro % git log --oneline
00cb66a (HEAD -> main) Revert "Borrado accidental"
5997190 Borrado accidental
cac76e2 Añadido capítulo 5 al índice.
a793a1d Añadido capitulo 3.
16e5caa Añadido capítulo 2.
9c60efa Añadido capítulo 1.
1e8e28c Añadido capítulo 3 sobre gestión de ramas al índice.
67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % git status
On branch main
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    capitulos/capitulo3.txt
        modified:   indice.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md

no changes added to commit (use "git add" and/or "git commit -a")
williamgalvis@WilliamalvisAir libro % git commit -m "Borrado accidentel"
[main bfef5c9] Borrado accidentel
 2 files changed, 1 insertion(+), 3 deletions(-)
 delete mode 100644 capitulos/capitulo3.txt
williamgalvis@WilliamalvisAir libro % git commit -m "Borrado accidentel"
[main bfef5c9] Borrado accidentel
 2 files changed, 1 insertion(+), 3 deletions(-)
 delete mode 100644 capitulos/capitulo3.txt
williamgalvis@WilliamalvisAir libro % git reset --hard cac76e23
HEAD is now at cac76e2 Añadido capítulo 5 al índice.
williamgalvis@WilliamalvisAir libro % 
```



## Ejercicios de gestión de ramas

### Ejercicio 1

Crear una nueva rama bibliografia y mostrar las ramas del repositorio.

```bash
williamgalvis@WilliamalvisAir libro % git checkout -b bibliografia
Switched to a new branch 'bibliografia'
williamgalvis@WilliamalvisAir libro % git branch
* bibliografia
  main
williamgalvis@WilliamalvisAir libro %    
```



### Ejercicio 2

Crear el fichero `capitulos/capitulo4.txt` y añadir el texto siguiente

En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje “*Añadido capítulo 4.*”

Mostrar la historia del repositorio incluyendo todas las ramas.

```bash
williamgalvis@WilliamalvisAir libro % git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .DS_Store
        README.md
        capitulos/capitulo4.txt

nothing added to commit but untracked files present (use "git add" to track)
williamgalvis@WilliamalvisAir libro % git add capitulos/capitulo4.txt 
williamgalvis@WilliamalvisAir libro % git commit -m "Añadido capítulo 4."
[main 7de8087] Añadido capítulo 4.
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 capitulos/capitulo4.txt
 williamgalvis@WilliamalvisAir libro % git log --graph --oneline
* 7de8087 (HEAD -> main) Añadido capítulo 4.
* cac76e2 (bibliografia) Añadido capítulo 5 al índice.
* a793a1d Añadido capitulo 3.
* 16e5caa Añadido capítulo 2.
* 9c60efa Añadido capítulo 1.
* 1e8e28c Añadido capítulo 3 sobre gestión de ramas al índice.
* 67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 3

Cambiar a la rama bibliografia.

Crear el fichero `bibliografia.txt` y añadir la siguiente referencia

```
Chacon, S. and Straub, B. Pro Git. Apress.
```

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje “*Añadida primera referencia bibliográfica.*”

Mostrar la historia del repositorio incluyendo todas las ramas.

```bash
williamgalvis@WilliamalvisAir libro % git checkout bibliografia                 
Switched to branch 'bibliografia'
williamgalvis@WilliamalvisAir libro % git log --all --decorate --graph --oneline
* 62117cd (HEAD -> bibliografia) Añadida primera referencia bibliográfica.
| * 7de8087 (main) Añadido capítulo 4.
|/  
* cac76e2 Añadido capítulo 5 al índice.
* a793a1d Añadido capitulo 3.
* 16e5caa Añadido capítulo 2.
* 9c60efa Añadido capítulo 1.
* 1e8e28c Añadido capítulo 3 sobre gestión de ramas al índice.
* 67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 4

Fusionar la rama bibliografia con la rama master.

Mostrar la historia del repositorio incluyendo todas las ramas.

Eliminar la rama bibliografia.

Mostrar de nuevo la historia del repositorio incluyendo todas las ramas.

```
williamgalvis@WilliamalvisAir libro % git log --decorate --all --oneline --graph
* dfb46f0 (HEAD -> main) Merge bibliografia
* 7de8087 Añadido capítulo 4.
| * 62117cd (bibliografia) Añadida primera referencia bibliográfica.
|/  
* cac76e2 Añadido capítulo 5 al índice.
* a793a1d Añadido capitulo 3.
* 16e5caa Añadido capítulo 2.
* 9c60efa Añadido capítulo 1.
* 1e8e28c Añadido capítulo 3 sobre gestión de ramas al índice.
* 67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % git branch -d bibliografia
error: The branch 'bibliografia' is not fully merged.
If you are sure you want to delete it, run 'git branch -D bibliografia'.
williamgalvis@WilliamalvisAir libro % git branch -D bibliografia
Deleted branch bibliografia (was 62117cd).
williamgalvis@WilliamalvisAir libro % git log --decorate --all --oneline --graph
* dfb46f0 (HEAD -> main) Merge bibliografia
* 7de8087 Añadido capítulo 4.
* cac76e2 Añadido capítulo 5 al índice.
* a793a1d Añadido capitulo 3.
* 16e5caa Añadido capítulo 2.
* 9c60efa Añadido capítulo 1.
* 1e8e28c Añadido capítulo 3 sobre gestión de ramas al índice.
* 67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % 
```



### Ejercicio 5

Crear la rama bibliografia.

Cambiar a la rama bibliografia.

Cambiar el fichero `bibliografia.txt` para que contenga las siguientes referencias:

```
Scott Chacon and Ben Straub. Pro Git. Apress.
Ryan Hodson. Ry’s Git Tutorial. Smashwords (2014)
```

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “*Añadida nueva referencia bibliográfica.*”

Cambiar a la rama master.

Cambiar el fichero `bibliografia.txt` para que contenga las siguientes referencias:

```
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
```

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “*Añadida nueva referencia bibliográfica*.”

Fusionar la rama bibliografia con la rama master.

Resolver el conflicto dejando el fichero `bibliografia.txt` con las referencias:

```
Chacon, S. and Straub, B. Pro Git. Apress.
Loeliger, J. and McCullough, M. Version control with Git. O’Reilly.
Hodson, R. Ry’s Git Tutorial. Smashwords (2014)
```

Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “*Resuelto conflicto de bibliografía.*”

Mostrar la historia del repositorio incluyendo todas las ramas.

```bash
williamgalvis@WilliamalvisAir libro % git log --all --decorate --graph --oneline
*   c308c32 (HEAD -> main, biblografia) Resuelto conflicto de bibliografia
|\  
| * 7a6f546 Añadida nueva referencia biblografica
* | 8d04c34 Añadida nueva referencia biblografica
|/  
* dfb46f0 Merge bibliografia
* 7de8087 Añadido capítulo 4.
* cac76e2 Añadido capítulo 5 al índice.
* a793a1d Añadido capitulo 3.
* 16e5caa Añadido capítulo 2.
* 9c60efa Añadido capítulo 1.
* 1e8e28c Añadido capítulo 3 sobre gestión de ramas al índice.
* 67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % 
```



## Ejercicios de repositorios remotos

### Ejercicio 1

Crear un nuevo repositorio público en GitHub con el nombre `libro-git`.

Añadirlo al repositorio local del libro.

Mostrar todos los repositorios remotos configurados.

```
williamgalvis@WilliamalvisAir libro % git remote add origin https://github.com/wicho120/libro-git.git                       
williamgalvis@WilliamalvisAir libro % git push -u origin main
Enumerating objects: 37, done.
Counting objects: 100% (37/37), done.
Delta compression using up to 8 threads
Compressing objects: 100% (32/32), done.
Writing objects: 100% (37/37), 3.91 KiB | 3.91 MiB/s, done.
Total 37 (delta 6), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (6/6), done.
To https://github.com/wicho120/libro-git.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 2

Añadir los cambios del repositorio local al repositorio remoto de GitHub.

Acceder a GitHub y comprobar que se han subido los cambios mostrando el historial de versiones.

```bash
williamgalvis@WilliamalvisAir libro % git log --all --decorate --graph --oneline                     
*   c308c32 (HEAD -> main, origin/main, biblografia) Resuelto conflicto de bibliografia
|\  
| * 7a6f546 Añadida nueva referencia biblografica
* | 8d04c34 Añadida nueva referencia biblografica
|/  
* dfb46f0 Merge bibliografia
* 7de8087 Añadido capítulo 4.
* cac76e2 Añadido capítulo 5 al índice.
* a793a1d Añadido capitulo 3.
* 16e5caa Añadido capítulo 2.
* 9c60efa Añadido capítulo 1.
* 1e8e28c Añadido capítulo 3 sobre gestión de ramas al índice.
* 67be86d Añadido indice del libro
williamgalvis@WilliamalvisAir libro % 
```

### Ejercicio 3

Colaborar en el repositorio remoto `libro-git` de otro usuario.

Clonar su repositorio `libro-git`.

Añadir el fichero `autores.txt` que contenga el nombre del usuario y su correo electrónico.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje “*Añadido autor.*”

Subir los cambios al repositorio remoto.

### Ejercicio 4

Hacer una bifurcación del repositorio remoto `asalber/libro-git` en GitHub.

Clonar el repositorio creado en la cuenta de GitHub del usuario.

Crear una nueva rama autoria y activarla.

Añadir el nombre del usuario y su correo al fichero `autores.txt`.

Añadir los cambios a la zona de intercambio temporal.

Hacer un commit con el mensaje “*Añadido nuevo autor.*”

Subir los cambios de la rama autoria al repositorio remoto en GitHub.

Hacer un Pull Request de los cambios en la rama autoria.
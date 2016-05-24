# EJERCICIOS GIT, GITHUB Y MARKDOWN #

## 1. Utilización básica de Git, GitHub y Markdown ##

### 1.1. Crear repositorio ###

![](/images/new_repository.png)

### 1.2. Clonar repositorio ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git clone https://github.com/japegon/campusciff.git
~~~

### 1.3. Commit inicial ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git add README.md
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git commit -m "commit inicial"
~~~

![](/images/commit_inicial.png)

### 1.4. Push inicial ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git push -u origin master
~~~

![](/images/push_inicial.png)

### 1.5. Ignorar archivos ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ cat .gitignore 
$GIT_DIR/privada/
/privado.txt
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git add -A
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git commit -m "ficheros privados"
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git push -u origin master
~~~

En la carpeta vemos que aparecen los ficheros, aunque Git no los haya subido: 

![](/images/ficheros_privados.png)

### 1.6. Crear etiqueta ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git tag v0.1
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git commit -m "etiqueta"
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git push -u origin master
~~~

### 1.7. Cuenta de GitHub ###

#### Poner una foto ####

En la página de perfil nos da la posibilidad de cambiar nuestro avatar.

![](/images/Foto.png "Foto de perfil")

#### Doble factor ####

Activamos el doble factor usando SMS.

![](/images/doble_factor2.png "Doble factor activado")

#### Clave pública ####

Creamos una clave pública para nuestro ordenador y la añadimos al perfil de GitHub

~~~
japegon@japegon-W230ST:~/Descargas/gnupg-2.0.30$ gpg --gen-key
~~~

![](/images/Clave_GPG.png "Clave pública")

Configuramos la clave:

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git config --global user.signingkey CD4E172A
~~~

### 1.8. Uso social ###

#### Seguir a compañeros de clase ####

![](/images/following.png "Following")

#### Seguir los repositorios campusciff ####

![](/images/watchlist.png "Watch list")

#### Añadir una estrella a los repositorios campusciff ####

![](/images/stars.png "Starred")

### 1.9. Crear una tabla ###

|NOMBRE|GITHUB|
|------|-----:|
|Jorge Maza|<https://github.com/jorgemaza/campusciff>|
|Juan Isidro|<https://github.com/JuanRodriguez16/campusciff>|
|Araceli Macia|<https://github.com/araceliMacia/campusciff>|

### 1.10. Colaboradores ###

![](/images/Colaborador.png "Colaborador")

## 2. Utilización avanzada de Git, GitHub y Markdown ##

### 2.1. Crear una rama ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git checkout -b v0.2
~~~

**Ramas:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git branch -v
  master 67186dc readme
* v0.2   69c4a27 fichero 2
~~~

### 2.2. Añadir fichero 2.txt ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ touch 2.txt
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git add -A
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git commit -m "fichero 2"
[v0.2 556743a] fichero 2
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 2.txt
~~~

**Subir los cambios:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git push origin v0.2
Counting objects: 5, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 785 bytes | 0 bytes/s, done.
Total 5 (delta 3), reused 0 (delta 0)
To https://github.com/japegon/campusciff.git
 * [new branch]      v0.2 -> v0.2
~~~

### 2.3. Merge directo ###

**Posicionarse en rama master:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git checkout master
Switched to branch 'master'
Su rama está actualizada con «origin/master».
~~~

**Merge de v0.2 en rama master:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git merge v0.2 -m "Merge con la rama master"
Updating 67186dc..1c0acc1
Fast-forward (no commit created; -m option ignored)
 2.txt     |  0
 README.md | 58 ++++++++++++++++++++++++++++++++++++++++++++--------------
 2 files changed, 44 insertions(+), 14 deletions(-)
 create mode 100644 2.txt
~~~

### 2.4. Merge con conflicto ###

**Poner Hola en el fichero 1.txt:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ echo "Hola" > 1.txt
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git add -Ajapegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git commit -m "Hola en fichero 1.txt"
[master e52b063] Hola en fichero 1.txt
 1 file changed, 1 insertion(+)
~~~

**Posicionarse en rama v0.2:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git checkout v0.2
Switched to branch 'v0.2'
~~~

**Poner Adios en el fichero 2.txt:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ echo "Adios" > 1.txt
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git add -Ajapegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git commit -m "Adios en fichero 1.txt"
[v0.2 4d8bc8c] Adios en fichero 1.txt
 1 file changed, 1 insertion(+)
~~~

**Hacer merge con conflicto:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git checkout master
Switched to branch 'master'
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git merge v0.2 -m "Merge con conflicto"
Automezclado 1.txt
CONFLICTO(contenido): conflicto de fusión en 1.txt
Automatic merge failed; fix conflicts and then commit the result.
~~~

### 2.5. Listado de ramas ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git branch --merged
* master
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git branch --no-merged
  v0.2
~~~

### 2.6. Arreglar conflicto ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ cat 1.txt
<<<<<<< HEAD
Hola
=======
Adios
>>>>>>> v0.2
~~~

Modificamos el fichero 1.txt:

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ cat 1.txt
Adios
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git add -Ajapegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git commit -m "Arreglado conflicto"
[master ca9ebaa] Arreglado conflicto
~~~

### 2.7. Borrar rama ###

**Crear tag:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git tag v0.2
~~~

**Borrar rama v0.2:**

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git branch -d v0.2
Eliminada la rama v0.2 (era 4d8bc8c)
~~~

### 2.8. Listado de cambios ###

Lo hacemos a partir de un alias list

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git config --global alias.list 'log --oneline --decorate --graph --all'
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git list*   ca9ebaa (HEAD -> master, tag: v0.2) Arreglado conflicto
|\  
| * 4d8bc8c Adios en fichero 1.txt
* | e52b063 Hola en fichero 1.txt
|/  
* 1c0acc1 (origin/v0.2) fichero 2
* 69c4a27 fichero 2
* 556743a fichero 2
* 67186dc (origin/master) readme
* f4730f0 readme
* e256ec2 images
* 63e7078 images
* 1ed79f0 images
* cc3ff2b images
* 01f201e images
* 9acd3b6 prueba final
* 1fc6aa6 etiqueta
* d995a65 (tag: v0.1) ficheros privados
* 766a115 ficheros privados
* 968b135 ficheros privados
* 66ca4ed ficheros privados
* 26a0b53 commit inicial
~~~

### 2.9. Crear una organización ###

![](/images/organizacion.png "Organización")

### 2.10. Crear equipos ###

Grupo administradores:

![](/images/grupo_administradores.png "Administradores")

Grupo colaboradores:

![](/images/grupo_colaboradores.png "Colaboradores")

Permisos grupos:

![](/images/permisos_grupos.png "Colaboradores")

**Meter compañeros en los equipos:**



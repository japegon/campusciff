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

### 2.2. Añadir fichero 2.txt ###

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ touch 2.txt
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git add -A
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git commit -m "fichero 2"
[v0.2 556743a] fichero 2
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 2.txt
~~~

Subir los cambios:

~~~
japegon@japegon-W230ST:/media/japegon/Datos/Máster/github/campusciff$ git push origin v0.2
~~~

# Utilización básica de Git, GitHub y Markdown #
## Clonar repositorio ##

Comandos:

git clone https://github.com/japegon/campusciff.git

## Commit inicial ##

Comandos:

git add README.md

git commit -m "commit inicial"

Bash: ![Commit inicial](/images/commit_inicial.png)

## Push inicial ##

Comandos:

git push -u origin master

Bash: ![Push inicial](/images/push_inicial.png)

## Ignorar archivos ##

Comandos:

gedit .gitignore
	$GIT_DIR/privada
	/privado.txt

git add -A

git commit -m "ficheros privados"

git push -u origin master

En la carpeta vemos que aparecen los ficheros, aunque Git no los haya subido: ![Ficheros privados](/images/ficheros_privados.png)

## Crear etiqueta ##

Comandos:

git tag v0.1

git commit -m "etiqueta"

git push -u origin master

## Cuenta de GitHub ##

- **Poner una foto**: En la página de perfil nos da la posibilidad de cambiar nuestro avatar.

![Foto de perfil](/images/Foto.png "Foto de perfil")

- **Doble factor**: Activamos el doble factor usando SMS.

![Doble factor activado](/images/doble_factor2.png "Doble factor activado")

- **Clave pública**: Creamos una clave pública para nuestro ordenador y la añadimos al perfil de GitHub

Comandos:

gpg --gen-key

![Clave pública](/images/Clave_GPG.png "Clave pública")

Configuramos la clave:

![Configuración](/images/GPG.png)

## Uso social ##

|NOMBRE|GITHUB|
|------|-----:|
|Nombre del compañero 1|enlace|
|Nombre del compañero 2|enlace|

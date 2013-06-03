Repositorio de ejemplo para la exposición sobre git, usuando GitHub como servidor
de alojamiento. Además para actualizar los archivos se usa SSH


************************ Pasos Generales  ************************

1. Actualizamos los repositorios mediante apt-get update

2. Instalamos la git mediante apt-get install git

3. Configuramos el nombre de usuario y email de este mediante 
git config --global user.name "Edwin"
git config --global user.email "edwin.cr90@gmail.com"

4. Mediante git config --list podemos observar que se ha configurado correctamente ul usuario y el email.También podemos observar otros párametros se han configurado y se pueden configurar.

5. Reinicializamos el el repositorio de git (Git repository) en el home del usuario. /home/usuario/.git/

6. Clonamos el repositorio ya creado en GitHub mediante 
git clone https://github.com/eduflocas/ejemplo_uso_git.git. Esto crea un directorio en /home/usuario/ejemplo_uso_git

7.Accedemos al directorio ejemplo_uso_git y modificamos algún archivo(en este caso helloworld.cpp), luego lo guardamos y luego se prepara el archivo para actualizarlo en GitHub

8. git add helloworld.cpp

7. Con git status nos damos cuenta que el archivo esta preparado para dar hacer la confirmación (commit)

8. Luego se realiza la confirmación mediante git commit -am "nuevo cambio en hello world"

9. Con git status, podemos observar que los cambios ha sido confirmados 

10. Para actualizar los archivos en GitHub, se puede hacer mediante 2 posibles opciones:

   a. git push https://github.com/eduflocas/ejemplo_uso_git.git
   b. Mediante ssh: 
        - cd ~/.ssh
        - ssh-keygen -t rsa -C "edwin.cr90@gmail.com"
        - Passphrase: ejemplo_git
        - cat ~/.ssh/id_rsa.pub
        - Copiamos la llave pública y la colocamos en 
          Account Settings/SSH Keys/Add SSH key. Se le coloca un título
         y se copia la llave pública
        - Luego se confirma que la conexión ssh esta establecida mediante 
          ssh -T git@github.com. Esto debe mostrar un mensaje de autenticación exitosa
 11. Para actualizar los archivos en el repositorio en GitHub, se ejecuta el siguiente comando:
git push git@github.com:eduflocas/ejemplo_uso_git.git
   * Debemos escribir el passphrase
   

Nota:

-> Para observar la bitacora de acciones que se han realizado se ejecuta el comando git log ó git log --summary (q: para salir)
-> Comando util para observar que cambio se encuentra preparado para confirmar: git diff HEAD
-> Para deshacer los cambios en los archivos después de haber ejecutado git add
      git reset --soft HEAD^     # use --soft if you want to keep your changes
      git reset --hard HEAD^     # use --hard if you don't care about keeping the changes you made

->Para descartar cambios: git checkout --README.md
-> Antes configurar el ssh para no tener problemas

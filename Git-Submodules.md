# Gestión de Sub módulos en Github

## Tabla de contenidos:

- [Prerequisitos](#Prerequisites)
- [Modo local](#modo-local)
- [Modo remoto](#modo-remoto)

### Prerequisitos

1. Tener instalado una versión de git, podemos verificar en nuestro entorno local con el siguiente comando:

   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules> git --version
   git version 2.33.1.windows.1
   ```

   En caso de no tener ninguna versión instalada puedes obtener la [última versión desde este link](https://dotnet.microsoft.com/en-us/download/dotnet/3.1) y proceder a instalarla en tu entorno local.

2. Tener una cuenta en [Github](https://github.com/).

### Modo local

Esta sección explica como crear submódulos a un repositorio de manera local, para esto debemos seguir los siguientes pasos.

1. Creamos la carpeta contenedora del repositorio base con el siguiente comando:

   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules> mkdir base


    Directory: G:\Trabajo\FSA-Group\Git-Submodules


   Mode                 LastWriteTime         Length Name
   ----                 -------------         ------ ----
   d-----        10/13/2023   8:18 PM                base


   PS G:\Trabajo\FSA-Group\Git-Submodules>
   ```

2. Nos posicionamos dentro de la carpeta recien creada:
   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules> cd base
   ```
3. Inicializamos un repositorio de git con el siguiente comando:
   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git init
   Initialized empty Git repository in G:/Trabajo/FSA-Group/Git-Submodules/base/.git/
   PS G:\Trabajo\FSA-Group\Git-Submodules\base>
   ```
4. Incorporamos algunos ficheros al repositorio recien creado.

5. Listamos el contenido del mismo:

   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> dir


    Directory: G:\Trabajo\FSA-Group\Git-Submodules\base


   Mode                 LastWriteTime         Length Name
   ----                 -------------         ------ ----
   -a----         6/18/2022   9:13 PM          49609 Me.png
   -a----         8/23/2023   9:57 AM            646 Reactjs.txt
   -a----          3/2/2022  10:22 AM         111576 Utilice la función CDC de SQLServer 2008 para realizar la captura de cambios de datos -
                                                   programador clic.html


   PS G:\Trabajo\FSA-Group\Git-Submodules\base>
   ```

6. Para añadir el repositorio al [staging area](https://keepcoding.io/blog/que-es-staging-area-y-para-que-sirve/#:~:text=El%20Staging%20Area%20de%20Git%2C%20o%20git%20staged%20area%2C%20es,en%20el%20repositorio%20en%20producci%C3%B3n.), ejecutamos el siguiente comando:

   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git add .
   ```

7. Guardamos los cambios de forma permanente, ejecutando el siguiente comando:

   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git commit -m "Commit inicial"
   [master (root-commit) e0b6771] Commit inicial
   3 files changed, 1455 insertions(+)
   create mode 100644 Me.png
   create mode 100644 Reactjs.txt
   create mode 100644 "Utilice la funci\303\263n CDC de SQLServer 2008 para realizar la captura de cambios de datos - programador clic.html"
   PS G:\Trabajo\FSA-Group\Git-Submodules\base>
   ```

8. Accedemos a [Github](https://github.com/) mediante nuestra cuenta de usuario y creamos el repositorio correspondiente que contendrá el contenido de nuestro repositorio base local. Para este caso estaré utilizando el repositorio https://github.com/potlitel/base_repo

9. Para subir los cambios a nuestro repositorio remoto, ejecutamos lo siguiente:

   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git remote add origin git@github.com:potlitel/base_repo
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git push -u origin master
   ```

   Si luego de la ejecución de este último comando, recibes un error similar al siguiente:

   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git push -u origin master
   git@github.com: Permission denied (publickey).
   fatal: Could not read from remote repository.

   Please make sure you have the correct access rights
   and the repository exists.
   PS G:\Trabajo\FSA-Group\Git-Submodules\base>
   ```

   Ejecutas los siguientes comandos y debes obtener el mismo resultado satisfactorio como se muestra seguidamente:

   ```sh
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git remote set-url origin https://github.com/potlitel/base_repo.git
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git remote -v
   origin  https://github.com/potlitel/base_repo.git (fetch)
   origin  https://github.com/potlitel/base_repo.git (push)
   PS G:\Trabajo\FSA-Group\Git-Submodules\base> git push -u origin master
   Enumerating objects: 5, done.
   Counting objects: 100% (5/5), done.
   Delta compression using up to 4 threads
   Compressing objects: 100% (5/5), done.
   Writing objects: 100% (5/5), 68.45 KiB | 17.11 MiB/s, done.
   Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
   To https://github.com/potlitel/base_repo.git
   * [new branch]      master -> master
   Branch 'master' set up to track remote branch 'master' from 'origin'.
   PS G:\Trabajo\FSA-Group\Git-Submodules\base>
   ```

10. Verificamos el historial de commits realizados mediante el siguiente comando:

    ```sh
    PS G:\Trabajo\FSA-Group\Git-Submodules\base> git log --oneline
    e0b6771 (HEAD -> master, origin/master) Commit inicial
    PS G:\Trabajo\FSA-Group\Git-Submodules\base>
    ```

11. Desde la raíz de la carpeta del repositorio base, creamos la carpeta del repositorio "submodulo" de nuestro repositorio base:

    ```sh
    PS G:\Trabajo\FSA-Group\Git-Submodules\base> mkdir standard_repo


     Directory: G:\Trabajo\FSA-Group\Git-Submodules\base


    Mode                 LastWriteTime         Length Name
    ----                 -------------         ------ ----
    d-----        10/13/2023  10:12 PM                standard_repo


    PS G:\Trabajo\FSA-Group\Git-Submodules\base>
    ```

12. Volvemos a ejecutar los pasos 2 al 10 anteriomente listados

13. Regresamos a la raiz del repositorio base:
    ```sh
    PS G:\Trabajo\FSA-Group\Git-Submodules\base\standard_repo> cd ..
    PS G:\Trabajo\FSA-Group\Git-Submodules\base>
    ```
14. Ejecutamos el siguiente comando:
    ```sh
    PS G:\Trabajo\FSA-Group\Git-Submodules\base> git submodule add ./standard_repo
    Adding existing repo at 'standard_repo' to the index
    PS G:\Trabajo\FSA-Group\Git-Submodules\base>
    ```
15. Verificamos que se haya creado el submodulo correspondiente:
    ```sh
    PS G:\Trabajo\FSA-Group\Git-Submodules\base> git status
    On branch main
    Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
         new file:   .gitmodules
         new file:   standard_repo
    PS G:\Trabajo\FSA-Group\Git-Submodules\base>
    ```
16. Adicionamos los cambios:

    ```sh
    PS G:\Trabajo\FSA-Group\Git-Submodules\base> git add .
    ```

17. Ejecutamos commit:

    ```sh
    PS G:\Trabajo\FSA-Group\Git-Submodules\base> git commit -m "Se adiciona submodulo al repo base"
    [main d6d2f1e] Se adiciona submodulo al repo base
    2 files changed, 4 insertions(+)
    create mode 100644 .gitmodules
    create mode 160000 standard_repo
    PS G:\Trabajo\FSA-Group\Git-Submodules\base>
    ```

18. Finalizamos subiendo los cambios realizados:
    ```sh
    PS G:\Trabajo\FSA-Group\Git-Submodules\base> git push --set-upstream origin main
    Enumerating objects: 4, done.
    Counting objects: 100% (4/4), done.
    Delta compression using up to 4 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 376 bytes | 376.00 KiB/s, done.
    Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
    To https://github.com/potlitel/base_repo.git
      e0b6771..d6d2f1e  main -> main
    Branch 'main' set up to track remote branch 'main' from 'origin'.
    ```

### Modo remoto

This section provide a step-by-step description of how to get the development environment running.

1. Clone the repo with the following command.
   ```sh
   git clone https://github.com/potlitel/HR-Management.git
   ```

````

2. Position yourself inside the newly cloned repo folder.
   ```sh
   cd HR-Management
   ```
3. Execute the following command
   ```sh
   dotnet restore
   ```
4. Open the project solution file (HR-Management.sln) using Visual Studio.
````

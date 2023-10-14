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

### Modo remoto

This section provide a step-by-step description of how to get the development environment running.

1. Clone the repo with the following command.
   ```sh
   git clone https://github.com/potlitel/HR-Management.git
   ```
2. Position yourself inside the newly cloned repo folder.
   ```sh
   cd HR-Management
   ```
3. Execute the following command
   ```sh
   dotnet restore
   ```
4. Open the project solution file (HR-Management.sln) using Visual Studio.

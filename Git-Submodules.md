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

5. Right click on the 'HR-Management-Database' Database project and click on the 'Publish...' option. Remember to modify the connection string (appsettings.json) according to your environment. Make sure that the output of this command is similar to the following:

   ```sh
   Publish completed successfully
   ```

6. Run the project 'HR-Management-WebAPI' and voila, enjoy it.

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

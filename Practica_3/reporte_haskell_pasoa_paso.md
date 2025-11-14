
# Reporte de práctica: Instalación y uso de Haskell para aplicación TODO

## Instalación del entorno Haskell

1. Visitar la página oficial de descargas de Haskell ([Downloads]). Aquí se indica que GHCup es la herramienta recomendada para instalar todo el entorno.
2. Acceder a la página de GHCup mediante su enlace oficial.
3. Copiar el comando de instalación que proporciona GHCup.
4. Abrir una ventana de PowerShell (sin modo administrador) y pegar el comando para ejecutar la instalación de GHCup.
5. Con GHCup instalado, utilizarlo para instalar las herramientas necesarias:
   - Compilador GHC
   - Intérprete Hugs
   - Haskell Language Server (HLS)
   - Stack (manejador de paquetes y construcción)
   - Cabal (herramienta de empaquetado y construcción)
6. Verificar instalación correcta ejecutando comandos: `ghc --version`, `stack --version` y `cabal --version`.
7. Seguir la guía oficial de inicio ([Get Started]) para una introducción rápida y para confirmar que todo funciona.

## Preparación y uso de la aplicación TODO en Haskell

1. Crear un nuevo proyecto en Stack con:
```
stack new todo
```
2. Explorar los archivos principales:
   - `app/Main.hs`: control principal de la aplicación.
   - `src/Lib.hs`: funcionalidades y lógica.
   - `package.yaml`: configuración y dependencias.
3. Editar `package.yaml` para incluir librerías requeridas como `dotenv` y `open-browser`.
4. Compilar el proyecto con:
```
stack build
```
5. Ejecutar la aplicación con:
```
stack run
```
6. Interactuar con la aplicación usando comandos:
   - `+ texto`: añadir tarea
   - `- número`: eliminar tarea
   - `l`: listar tareas
   - `e número`: editar tarea
   - `s número`: mostrar tarea
   - `r`: invertir lista
   - `c`: limpiar lista
   - `q`: salir
7. Crear un archivo `.env` para definir variables como `URL` que pueden abrirse desde la app.


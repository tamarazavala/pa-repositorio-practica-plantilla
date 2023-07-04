# Dependencias del proyecto

Carpeta para registrar los módulos que necesiten ser instalados para que nuestro proyecto sea reproducible.

# Uso de entornos visuales

Un "Entorno" en Python es el contexto en el que se ejecuta un programa de Python que consta de un intérprete y una cantidad de paquetes instalados.

## Entorno global:
Por defecto, cualquier intérprete de Python instalado se ejecuta en su propio entorno global. Por ejemplo, si se ejecuta el comando python o python3 en alguna terminal (dependiendo de cómo se haya instalado Python), se estaría ejecutando en el entorno global de ese intérprete. Cualquier paquete que se instale o desinstale afecta el entorno global y por tanto todos los programas que se ejecutan en él.

En Python, es una buena práctica crear un entorno específico de un espacio de trabajo o entorno virtual local.

## Entorno virtual local:
Este tipo de entorno te permite instalar módulos de python sin afectar otros entornos aislando la instalación de los módulos del espacio de trabajo. 

## Creación de entorno virtual local en VSCode

- Abrir la paleta de comandos, __Command Palette__ (`Ctrl+Shift+P`). Buscar y seleccionar el comando **Python: Create Environment**

![image](https://github.com/Grupo-de-Computacion-de-la-FI-UNER/pa-repositorio-practica-inicial/assets/69655502/e951cfc3-929b-4f2d-ae58-01907f988e30)

- Una vez seleccionado el comando, se presenta una lista de tipos de entornos: **Venv** o **Conda**
 
![image](https://github.com/Grupo-de-Computacion-de-la-FI-UNER/pa-repositorio-practica-inicial/assets/69655502/e50df50f-f5c9-446d-b73d-afc8ba422fec)

- Seleccionar el tipo de entorno **Venv**, el comando presenta una lista de los intérpretes disponibles que pueden utilizarse como base para el nuevo entorno virtual

![image](https://github.com/Grupo-de-Computacion-de-la-FI-UNER/pa-repositorio-practica-inicial/assets/69655502/fd4f8179-befd-4260-b4cb-04d104ebb593)

- Luego de seleccionar el intérprete, se mostrará una notificación con el progreso de la creación de la carpeta del entorno

![image](https://github.com/Grupo-de-Computacion-de-la-FI-UNER/pa-repositorio-practica-inicial/assets/69655502/3dfa9981-1901-4218-8b58-fd63aca44ecb)

- Una vez creado nuestro entorno virtual, el mismo debe ser activado usando el siguiente comando en la terminal de VSCode:
  `& .venv\Scripts\Activate.ps1`

### ⚠️ 
En Windows al ejecutar el comando anterior nos puede aparecer el mensaje:
"File D:\ProgAvanzadaPython\Ejercicios\TrabajoPractico_1\.venv\Scripts\Activate.ps1 cannot be loaded because running scripts is disabled on this system. 
For more information, see about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170." 
En este caso es necesario ingresar el siguiente comando en la terminal: 

`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process`

- Al ejecutar los comandos anteriores, aparece la etiqueta (.venv) en la entrada de comando indicando que se activó el entorno:
  
![image](https://github.com/Grupo-de-Computacion-de-la-FI-UNER/pa-repositorio-practica-inicial/assets/69655502/e7eb213b-c861-49bd-a81f-661734086727)

- Una vez activado nuestro entorno, podemos instalar los módulos necesarios para nuestro proyecto usando pip desde la terminal de VSCode.
  
- Para desactivar el entorno ejecutar `deactivate` en la terminal de VSCode

## Generación del archivo "requirements.txt"

"requirements.txt" es el archivo que guardará los nombres de los módulos instalados para nuestro proyecto, así como las versiones de los mismos.

Para generar este archivo en la carpeta `deps/` ejecutar en la terminal de VSCode: 

`pip freeze > deps/requirements.txt`. 

Un archivo con ese nombre se creará en la carpeta correspondiente de nuestro proyecto. Un ejemplo del mismo se puede ver a continuación:

![image](https://github.com/Grupo-de-Computacion-de-la-FI-UNER/pa-repositorio-practica-inicial/assets/69655502/88ff5f05-b8c1-45cd-8c28-c31f3eed5999)

En el futuro se puede reproducir este entorno a partir del "requirements.txt", ejecutando el siguiente comando en un entorno virtual nuevo:

`pip install -r deps/requirements.txt`

# FLASK Backend API Test
A continuación se describe los pasos a seguir para la utilización de la API implementada, esta puede ser accedida desde el navegador, ya que se ha implementado una interfaz para poder probarse.

La versión de Python utilizada es la `v3.12.6` y ha sido desarrollado en Windows.

Para la ejecución de la API, seguir los siguientes pasos:

0. Se puede obtener el link del repositorio así:

![image](https://github.com/user-attachments/assets/6fbb0f96-d5ff-44c5-817b-7ec19022a061)

1. Clonar el repositorio:

    ```sh
    git clone https://github.com/dedetheprogrammer/flask-api-example.git
    ```

2. Moverse a la carpeta flask-api-example

    ```sh
    cd flask-api-example
    ```

3. Ejecutar alguno de los scripts. **Cualquiera de las dos formas es válida** y solo se requiere de una:

    - **A**. Directamente en el ordenador local:

        - Si se pueden ejecutar `Shell scripts` en Windows:
            ```sh
            chmod 0700 run.sh # Unicamente en Linux, no es necesario en Windows.
            ./run.sh
            ```

        - Si no se pueden ejecutar shell scripts y se pueden ejecutar `Powershell scripts`:
            ```
            run.ps1
            ```

        - Si no se puede ninguna:

            1. Instalar [Python 3.12.6](https://www.python.org/downloads/release/python-3126/).

            2. Crear un nuevo entorno virtual y copiar la carpeta de `app` dentro:

                ```sh
                python -m pip virtualenv # Unicamente si no se tiene ya instalado
                python -m venv flask-venv
                cp -r app flask-venv
                ```

            3. Activar el entorno virtual:

                ```sh
                cd flask-venv && .\Script\activate
                ```

            4. Instalar las dependencias:

                ```sh
                python -m pip install -r requirements.txt
                ```
            
            5. Iniciar el servidor:

                ```sh
                python app/server.py
                ```
            
            6. Para salir y limpiar los restos:

                ```sh
                deactivate
                cd ..
                rm -r flask-venv
                ```
    
    - **B**. Si se tiene Docker instalado:

        - Si se pueden ejecutar `Shell scripts` en Windows:
            ```sh
            chmod 0700 run.sh # Unicamente en Linux, no es necesario en Windows.
            ./docker-run.sh
            ```

        - Si no se pueden ejecutar Shell scripts y se pueden ejecutar `Powershell scripts`:
            ```
            docker-run.ps1
            ```

        - Si no se puede ninguna:

            1. Instalar [Docker](https://www.docker.com).

            2. Construir la imagen:
                ```sh
                docker build -t flask-api-example .
                ```
            
            3. Desplegar la imagen:
                ```sh
                docker run -it -p 127.0.0.1:8080:8080 flask-api-example
                ```

            4. Para finalizar, pulsar `Ctrl + C`. Obtener el nombre del contenedor para limpiar:
                ```sh
                docker ps -a
                 CONTAINER ID   IMAGE                 COMMAND              CREATED           STATUS                     PORTS     NAMES
                 ed908300dfc3   flask-api-example     "python server.py"   12 seconds ago    Exited (0) 2 seconds ago             modest_rosalind
                 af902bf47857   another-name          "python other.py"    3 minutes ago     Exited (0) 3 minutes ago             mystifying_morse
                ```

                Si Windows lo permite, se puede usar `grep` directamente:
                ```sh
                docker ps -a | grep 'flask-api-example'
                 ed908300dfc3   flask-api-example   "python server.py"   12 seconds ago   Exited (0) 2 seconds ago             modest_rosalind
                ```

            5. Buscar el contenedor cuya imagen sea `flask-api-example`, obtener su id y borrarlo (el ID no tiene porque ser el mismo, el nombre de imagen sí):
                ```sh
                docker rm ed908300dfc3
                ```
            
            6. Eliminar la imagen:
                ```sh
                docker rmi flask-api-example
                ```






3. Una vez ejecutado, la dirección definida por defecto es http://localhost:5000 o http://127.0.0.1:5000 que será accesible desde el navegador.



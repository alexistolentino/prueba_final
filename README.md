# prueba_final
# proyecto_dual
## 1. Repositorio en GitHub
## 2. Invitar a su compañero
## 3. configurar el repositorio para fastapi, groq, ollama
### 3.1 posible archivo requirements.txt
shell
fastapi
uvicorn[standard]
groq
ollama


bash
pip install -r requirements.txt

## 4. diseñar una API REST con las siguientes funciones
### 4.1 Enpoint que reciba un prompt, genere una respuesta y la envie al usuario

| *Punto*                | *Nombre*               | *Descripción*                                                                                                             |
|--------------------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| 1                        | *Description*          | Generar una respuesta a partir de un "prompt" proporcionado por el usuario                                                 |
| 2                        | *Summary*              | Procesa un prompt y genera una respuesta que se envía al usuario                                                           |
| 3                        | *Method*               | POST                                                                                                                     |
| 4                        | *Endpoint*             | http://localhost:8000/v1/respuesta                                                                               |
| 5                        | *Authentication*       | No aplica (NA)                                                                                                             |
| 6                        | *Query Param*          | No aplica (NA)                                                                                                             |
| 7                        | *Path Param*           | No aplica (NA)                                                                                                             |
| 8                        | *Data*                 | {"prompt": "porque el cielo es azul?"}                                                                                    |
| 9                        | *Status Code*          | 201 (Recurso creado con éxito)                                                                                           |
| 10                       | *Response Type*        | Application/json                                                                                                         |
| 11                       | *Response*             | {"message": "Respuesta generada para el prompt: porque el cielo es azul?"}                                                |
| 12                       | *Error Status Code*    | 400 (sintaxis inválida)                                                                                                  |
| 13                       | *Error Response Type*  | Application/json                                                                                                         |
| 14                       | *Error Response*       | {"message": "Datos invalidos"}                                                                                           |
| 15                       | *cURL*                 | curl -X POST -H "Content-Type: application/json" -d '{"prompt": "porque el cielo es azul?"}' http://localhost:8001/v1/respuesta |


### 4.2 Enpoint que reciba una imagen de 128px 128px, genere una descripcion de la imagen y la envie al usuario

| *Punto*                | *Nombre*               | *Descripción*                                                                                                             |
|--------------------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| 1                        | *Description*          | Generar una descripción de una imagen a partir de su URL                                                                    |
| 2                        | *Summary*              | Procesa una URL de imagen y genera una descripción que se envía al usuario                                                  |
| 3                        | *Method*               | POST                                                                                                                     |
| 4                        | *Endpoint*             | http://localhost:8000/v1/descripcion_imagen                                                                                  |
| 5                        | *Authentication*       | No aplica (NA)                                                                                                             |
| 6                        | *Query Param*          | No aplica (NA)                                                                                                             |
| 7                        | *Path Param*           | No aplica (NA)                                                                                                             |
| 8                        | *Data*                 | {"image_url": "https://ejemplo.com/imagen.jpg"}                                                                          |
| 9                        | *Status Code*          | 201 (Recurso creado con éxito)                                                                                           |
| 10                       | *Response Type*        | Application/json                                                                                                         |
| 11                       | *Response*             | {"message": "Descripción generada para la imagen en la URL: https://ejemplo.com/imagen.jpg"}                             |
| 12                       | *Error Status Code*    | 400 (sintaxis inválida)                                                                                                  |
| 13                       | *Error Response Type*  | Application/json                                                                                                         |
| 14                       | *Error Response*       | {"message": "Datos invalidos"}                                                                                           |
| 15                       | *cURL*                 | curl -X POST -H "Content-Type: application/json" -d '{"image_url": "https://ejemplo.com/imagen.jpg"}' http://localhost:8001/v1/descripcion_imagen |

## 5. Cada integrante desarrollara uno de los endpoints y lo integrara en el repositorio compartido

## 6. Estrategia para trabajar en equipo
### 6.1 trabajaremos en ramas, cada quien con su rama, para despues unir todo a la rama principal·

## 7. Comandos para instalar las dependencias
### 7.1 Antes de instalar liberias es recomendable actualizar pip, esto permite que se descarguen las últimas versiones de las librerías.
bash
(venv)$ pip install --upgrade pip

### 7.2 Instalar las librerias
Ejecuta estos comandos en la terminal de tu proyecto:
bash
pip install fastapi uvicorn requests python-dotenv pillow

### 7.3 Generar el archivo requirements.txt

Una vez que se instalaron las librerias se puede generar el archivo requirements.txt, este archivo permite llevar un control de las librerias instaladas y las versiones uitlizadas.

bash
(venv)$ pip freeze > requirements.txt

### 7.4 salir del ambiente virtual

Cuando ya no se requiera utilzar el ambiente virtual se puede salir con el siguiente comando

bash
deactivate

### 7.5 iniciar el entorno virtual

cuando se quiera iniciar de nuevo el entorno virtual utilizar el siguiente comando

bash
source venv/bin/activate

### 7.6  Crear el ambiente virtual

El ambiente virutal permite tener un espacio aislado donde se instalarán unicamente las librias necesarias, lo que permite evitar conflictos de versiones de librerias con otros proyectos.

bash
 python3 -m venv venv
 
## 8. conectar al servidor

bash
uvicorn main:app --reload


## 9.Ejemplo de prueba del 1er endpoint

bash
curl -X POST -H "Content-Type: application/json" -d '{"prompt": "porque el cielo es azul?"}' http://localhost:8001/v1/respuesta

## 10 Ejemplo de prueba del 2do enpoint

bash
curl -X POST -H "Content-Type: application/json" -d '{"image_path": "computadora.png"}' http://localhost:8001/v1/descripcion_imagen

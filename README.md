# Response-PaymentFormT1-Ipn

Este es un ejemplo de una creación de un endpoint con NODE.JS para poder utilizarlo con la [respuesta IPN (Instant Notification Payment)](https://secure.micuentaweb.pe/doc/es-PE/rest/V4.0/kb/payment_done.html) en la pasarela de pagos de Izipay. 


## Requisitos Previos

* Poder ingresar a su Back Office Vendedor. [Guía Aquí](https://github.com/izipay-pe/obtener-credenciales-de-conexion)

* Debe instalar la [versión de LTS node.js](https://nodejs.org/es/).

* Tener o crear una cuenta en [HEROKU](https://www.heroku.com/) (no tienen costo).

* OPCIONAL: tener una cuenta en [GitHub](https://github.com/).

## 1.- Crear el proyecto

  * Descargar el proyecto .zip haciendo click [Aquí](https://github.com/izipay-pe/Response-PaymentFormT1-Ipn/archive/refs/heads/main.zip) o clonarlo desde Git.  
  ```sh
  git clone https://github.com/izipay-pe/Response-PaymentFormT1-Ipn.git
  ``` 

  * Ingrese a la carpeta raíz del proyecto.

  * A continuación, instale Express y Morgan para poder ejecutar y ver las consultas en el servidor.

  ```bash
  npm i express morgan
  ```
  
  * Para poder probar si el servidor está operativo, ejecute el comando.

  ```bash
  npm run start
  ```
  
  puede ver el resultado en su servidor local: http://localhost:5000/respuesta/IPN
  

## 2.- Subirlo al servidor web

  Para este ejemplo se utilizó el servidor gratuito de [Heroku](https://www.heroku.com/), ingrese a su cuenta de Heroku y siga los siguientes pasos.

  * paso 1: creamos nuestro app, donde se subirá el proyecto.
          ![crear app](/src/imagenes-readme/crear-app.png)

  * paso 2: ingresamos un nombre para nuestro aplicativo y elegimos el servidor que más se adecue a nuestro proyecto, finalizamos dándole click a botón `"Create app"`.
          ![nombre app](/src/imagenes-readme/nombre-app.png)

  * paso 3: ingresamos a `"Deploy"`.
        ![deploy app](/src/imagenes-readme/deploy.png)

  * paso 4: Seleccionamos el método con el que subiremos el proyecto, tenemos 2 opciones:  
        ![deploy app](/src/imagenes-readme/metodo-deploy.png)    

    - 4.1.- Heroku CLI: seguir los pasos que indica.
      ![deploy app](/src/imagenes-readme/heroku-cli.png) 

    - 4.2.- Repositorio GitHub: se sincroniza con tu repositorio, buscas el nombre de tu proyecto y le das conectar.
      ![deploy app](/src/imagenes-readme/repositorio-git.png) 

      - cuando encuentre tu repositorio verificas tu rama y finalizas dándole click en el botón `"Deploy Branch"`
        ![deploy app](/src/imagenes-readme/finalizar.png) 

  * paso 5: Para visualizar nuestro proyecto le damos click en `"View"`.
      ![deploy app](/src/imagenes-readme/ver-IPN.png)  

    - A la ruta que se muestra añadimos nuestra ruta endpoin `"/respuesta/IPN"`, debería quedar de la siguiente manera:

      ```bash
      https://izpay-prueba.herokuapp.com/respuesta/IPN
      ```

## 3.- Configurar la URL de notificación al final del pago

  * Ingresar a su back office vendedor [aquí](https://secure.micuentaweb.pe/vads-merchant/) e ingresar a la siguiente ruta: `Configuración -> Reglas de notificaciones -> Url de notificación al final del pago`, una ves ingrese su endpoint, Guarda y acepta el mensaje de confirmación.

      ![Regla de Notificación](/src/imagenes-readme/rconfigurar-endpoint.png)
  

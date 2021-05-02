# Python Firebase
#### Ejemplo de Consulta y Registro en una base de datos en Firebase
se registro mediante el lenguaje de python en una base de datos no sql de firebase utilizando como extension el uso de las jupyter notebooks


## Teoria
[Firebase](https://firebase.google.com/) se trata de una  **plataforma móvil creada por Google, cuya principal función es desarrollar y facilitar la creación de apps de elevada calidad de una forma rápida**, con el fin de que se pueda aumentar la base de usuarios y ganar más dinero. La plataforma está subida en la nube y está disponible para diferente plataformas como  **iOS, Android y web**. Contiene diversas funciones para que cualquier desarrollador pueda combinar y adaptar la plataforma a medida de sus necesidades.

Firebase se inició cuando Google la compró en 2014, y seguidamente la fue mejorando mediante la compra del equipo de  [Divshot](https://divshot.com/).

## **Principales características de Firebase**

-   **Desarrollo**: Firebase permite la creación de mejores apps, minimizando el tiempo de optimización y desarrollo, mediante diferentes funciones, entre las que destacan la detección de errores y de testeo, que supone poder dar un salto de calidad a la app. Poder almacenar todo en la nube, testear la app o poder configurarla de manera remota, son características destacables de la plataforma.
-   **Analitica**: Tener un control máximo del rendimiento de la app mediante métricas analíticas, todo desde un único panel y de forma gratuita, es una de las ventajas que ofrece Firebase respecto a la  [analítica web](https://www.iebschool.com/blog/herramientas-analisis-web-analitica-usabilidad/ "analítica web"). Los datos analíticos que facilita Firebase, facilita la toma de decisiones basadas y fundamentadas en datos reales.
- -   **Poder de crecimiento**: Permite gestionar de manera fácil todos los usuarios de las aplicaciones, con el añadido de que se pueden captar nuevos usuarios, mediante invitaciones o notificaciones.
-   **Monetización**: Mediante  [AdMob](https://www.iebschool.com/blog/que-es-admob-como-ganar-dinero-mobile-marketing/ "AdMob"), Firebase permite que puedas ganar dinero.
-   **Rapidez:** Implementar Firebase puede ser fácil y rápido, gracias a su API que es muy intuitiva, sostenida en un solo SDK. Con Firebase puedes centrar tus esfuerzos en resolver los problemas de tus clientes y así poder evitar la pérdida de tiempo en la creación de una infraestructura compleja.
-   **Agilidad**: Firebase ofrece apps multiplataforma con una APIs integradas a SDK individuales para iOS, Android y Javascript, de tal forma que se puede gestionar diferentes apps sin necesidad de salir de la propia plataforma.

##### se importa la libreria de firebase y hacemos una consulta a la base de datos para al apartado de asistencia para ver los registros que se tienen .
```python
from firebase import firebase
db = firebase.FirebaseApplication("https://pythonfire-cb1ab-default-rtdb.firebaseio.com/",None)

result = db.get('/asistencia',  None)
```

##### creamos una clase en este caso es estudiante , de la clase estudiante necesitamos los atributos que mandaremos para hacer el registro para eso llenamos la instancia y con la funcion vars( ) seleccionamos el objeto que usaremos para tomar sus atributos y mediante el metodo post haremos el registro dentro de la base de datos
```python
class Student:

def  __init__(self,name,msj):
self.name = name
self.msj = msj
s1 =  Student("Jonathan","Si asisti a su clase")

data_s1 =  vars(s1)
db.post('/asistencia/',data_s1)
```

# Light Center

Aplicación móvil para agendar, modificar y cancelar citas de Light Center.

## Dependencias
[carousel_slider](https://pub.dev/packages/carousel_slider): Para agregar el carrusel de noticias/promociones de la empresa
Flutter Localizations (incluído en el SDK): Para agregar el idioma español a la aplicación

[Dart XML](https://pub.dev/packages/xml): Para facilitar el manejo de documentos XML en las solicitudes SOAP con el Web Service

[easy_pdf_viewer](https://pub.dev/packages/easy_pdf_viewer): Para visualizar archivos PDF desde el interior de la app (ideal cuando los usuarios no tienen una aplicación para lectura de estos archivos).

[flutter_expandable_fab](https://pub.dev/packages/flutter_expandable_fab): Para agregar el FAB animado sin escribir tanto código

[Flutter Spinkit](https://pub.dev/packages/flutter_spinkit): Para agregar Widgets adicionales

[Google Fonts](https://pub.dev/packages/google_fonts): Para agregar fuentes similares a las utilizadas por la empresa

[http](https://pub.dev/packages/http): Para agregar la funcionalidad de comunicación HTTP

[intl](https://pub.dev/packages/intl): Dependencia de apoyo para agregar el idioma español a la aplicación

[Jiffy](https://pub.dev/packages/jiffy): Dependencia de apoyo para el manejo de las fechas

[Isar](https://pub.dev/packages/isar): Para agregar una base de datos NoSQL

[path_provider](https://pub.dev/packages/path_provider): Dependencia de apoyo de la base de datos Isar.

[Table Calendar](https://pub.dev/packages/table_calendar): Para integrar los calendarios de la aplicación

[url_launcher](https://pub.dev/packages/url_launcher): Para agregar las funcionalidades de apertura de navegador, marcación por teléfono envío de mensajes, etc.

## Estructura General
La aplicación consta de diversas carpetas las cuales optarán por una estructura BLoc, con esto se busca optimizar la funcionalidad de la aplicación así como también su escalamiento al tener una estructura ordenada, las vistas o interfaces puden contener o no un controlador el cual le permitirá separar en su mayoría, la parte lógica de la visual, se manejará una estructura tal que el controlador de cada vista se llamará al igual que su capa visual agregando "_controller" en su nombre.

Ejemplo:
```
Vista: login.dart
Controlador: login_controller.dart
```

La estructura del programa se puede observar en los siguientes directorios:

### BusinessLogic
Esta carpeta contiene todos los elementos funcionales de la aplicación, es decir, toda la lógica de negocio, entre ellas encontramos
- Controllers: Aquí se encuentran diversos controladores para las vistas (pendiente por definir con Cubits)
- Cubits: Aquí se encuentran todas las clases que manejarán los estados del patrón BLoc

### Data
Esta carpeta contiene los modelos (clases) que integran el sistema tales como el usuario, las locaciones o clínicas y los tratamientos o pedidos del usuario. De igual forma, en esta carpeta se encuentran los repositorios que ejecutarán los métodos de los Cubits para cada una de las clases.

### Services
Esta carpeta contiene diferentes servicios de apoyo para la aplicación, ya sea con funciones generales así como el NavigationService, así como elementos de apoyo para las bases de datos, etc.

### Views
Esta carpeta contiene todos los elementos visuales (pantallas de la aplicación).

Dentro de la carpeta lib se podrán encontrar los siguientes archivos:
- colors: Actualmente, una extension para la clase Colors de Material Design, el objetivo de este archivo es proveer de forma sencilla los colores de la empresa, los cuales se utilizarán en la aplicación
- enums: Actualmente, una forma de agregar identificadores a la sección de comunicación HTTP (dicha función puede ser eliminada ya que la comunicación se realiza mediante el protocolo SOAP 1.1)
- extension: Actualmente, un archivo para agregar extensiones a clases predeterminadas tales como String, etc.
- main: Entry point de la aplicación, si se elimina la aplicación no funcionará por lo cual este archivo *no debe ser borrado*

Cuando se actualice o agregue un modelo, se debe correr el siguiente comando: `dart run build_runner build --delete-conflicting-outputs`.
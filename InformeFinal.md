## Seguridad en Bases de Datos basado en Framework de Ciberseguridad NIST ## 
###### Entrega 1 ######
Este proyecto pretende revisar el diseño/implementación/verificación de los principales aspectos de seguridad en bases de datos, teniendo como referencia el framework de Ciberseguridad de NIST  

Los principales actividades realizadas fueron:  
* Escoger un conjunto de datos que se pueda descargar de Internet.
* Describir investigar la organización dueña o generadora de los datos.
* Cargar el conjunto de datos en el DBMS.
* Aplicar todos los controles del NIST:  
   * Identify:
Información, datos, flujo de datos, seguridad, motores de bases de datos, clasificación
roles, terceros, legales, riesgos, vulnerabilidades, amenazas, planeación y pruebas. 
   * Protect:
Control de acceso, data-at-rest, data-in-transit, asset lifecycle, disponibilidad, fugas.
Integridad, líneas base, cambios, backups, mantenimiento remoto, logs, resiliencia.  

Los documentos disponibles en este repositorio son:  
1. Informe.md
2. Base de datos.sql
3. Flujo de datos.pdf
4. Riesgos.

CRITERIOS DE SELECCIÓN 

Con el objetivo de tener un contexto amplio que permita definir/implementar/revisar el marco de la implementación de la NIST, se definieron 4 criterios para la seleccion de la base de datos:

* La base de datos debe contener datos personales, estos hacen  relación a datos que se pueden asociar directamente a una persona y permite su identificación directa, entre ellos tenemos la dirección de residencia, dirección laboral, telefono personal. El tratamiento de los datos personales esta regulado bajo la legislación colombiana con la ley 1581 de 2012 y su decreto reglamentario 1377 de 2013. 
* La base de datos debe contener datos semiprivados, se caracterizan por interesar no sólo a su titular sino a cierto sector o grupo de personas, o a la sociedad en general, como el dato financiero y crediticio.
* La base de datos debe contener datos sensibles, son aquellos que pueden afectar la intimidad del titular y/o generar discriminación,  tales como aquellos que revelen la orientación política, las orientacion religiosa, la pertenencia a sindicatos, tambien los relativos a la salud, a la vida sexual, y los datos biométricos.
* La base de datos debe contener datos públicos, hace referencia a los datos relativos al estado civil de las personas, profesión y a su calidad de comerciante o de servidor público.


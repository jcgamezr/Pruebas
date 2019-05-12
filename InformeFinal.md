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

## CONTROL  ID.GV-4: Governance and risk management processes address cybersecurity risks
La organización cuenta con un proceso de gestión de riesgos, en donde se encuentran  definidos los siguientes

|CÓDIGO|RIESGO|DESCRIPCIÓN| 
|------|------|-----------------------------------| 
|RS-01|DEFINICIÓN DE ROL INADECUADA |El rol de monitoreo borro accidentalmente  data en la base datos de Contratos, impactando los procesos de la organizacion|  
|RS-02|FALTA DE CONCIENCIA DE SEGURIDAD |El administrador de la base datos de Contratos envió un correo a un destinatario equivocado con las credenciales  de acceso de la base datos.|
|RS-03|FALTA DE CAPACITACIÓN DE TRABAJO|"El administrador de la base datos de contratos no tiene la capitación en la última versión de SQL server| al momento de migrar la base de datos genera indisponibilidad.|"
|RS-04|FALTA DE MECANISMOS DE MONITOREO |El motor de base datos de SQL server en donde se encuentra la Base datos de Contratos no tiene un Rol de monitoreo. El área de monitoreo de la empresa no puede monitorear la base datos.|
|RS-05|PROTECCIÓN INADECUADA DE TRÁFICO SENSIBLE|La Red en donde se encuentra El motor de base datos de SQL server y que contiene la Base datos de contratos fue interceptada por ciberdelincuentes y robaron información sensible.| 
|RS-06 |ADMINISTRACIÓN DEFICIENTE DE CONTRASEÑA |El administrador de la base datos de Contratos guarda las credenciales de acceso en archivos de texto plano en el servidor.|
|RS-08|FALTA DE PROTECCIÓN CONTRA VIRUS Y CÓDIGO MALICIOSO |El servidor de la Base datos no tiene instalada una solución de antivirus|
|RS-09 |CONTROL DE ACCESO  INADECUADO DE BASE DE DATOS |Todos los usuarios del motor de Base datos de SQL tienen acceso a todos los roles,  cualquier usuario podría borrar una tabla de la BD de Contrato.| 

Se realiza la clasificación de los riesgos para identificar cuáles necesitan atención y corrección con mayor prioridad.

|CÓDIGO|RIESGO|PROBABILIDAD |IMPACTO |RESULTADO | 
|------|---------------|---- |---- |--------------- | 
|RS-01|DEFINICIÓN DE ROL INADECUADA |5|3|15 (Alto)|
|RS-02|FALTA DE CONCIENCIA DE SEGURIDAD |3|4|12 (Alto)|
|RS-03|FALTA DE CAPACITACIÓN DE TRABAJO|1|5|5 (Moderado)|
|RS-04|FALTA DE MECANISMOS DE MONITOREO |5|3|15 (Alto)|
|RS-05|PROTECCIÓN INADECUADA DE TRÁFICO SENSIBLE|3|5|15 (Alto)|
|RS-06 |ADMINISTRACIÓN DEFICIENTE DE CONTRASEÑA |4|3|12 (Alto)|
|RS-08|FALTA DE PROTECCIÓN CONTRA VIRUS Y CÓDIGO MALICIOSO |1|4|4 (Bajo)|
|RS-09 |CONTROL INADECUADO DE BASE DE DATOS |3|5|5 (Moderado)|



## CONTROL ID.RA-3: Threats, both internal and external, are identified and documented
## CONTROL PR.AC-4: Access permissions and authorizations are managed
## CONTROL PR.DS-2: Data-in-transit is protected
## CONTROL PR.DS-2: PR.IP-1: A baseline configuration of information technology systems is created and maintained



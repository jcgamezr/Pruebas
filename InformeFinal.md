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

## CONTROL ID.AM-5: Resources are prioritized based on their classification, criticality, and business value

La clasificación de la información en la base de datos se realiza según la información contenida en los campos de cada tabla en función de la confidencialidad, integridad, disponibilidad, requisitos legales aplicables, criticidad, divulgación, modificación	y valor para la organización. 

* Requisitos legales aplicables; hace referencia a la aplicabilidad de leyes o normas que protegen la información (1581, 052, 042, 1273).

* Criticidad; considera la información contenida en el campo como critica cuando es personal, semiprivada o sensible(C) y cuando la información es publica es considerada como no critica(NC). 

* Divulgación; se tienen 2 escenarios posibles en el primero la divulgación no causa peligro para la organización a corto plazo (D) y en el segundo escenario la divulgación tiene un impacto serio en los objetivos estratégicos a largo plazo (ND).

* Valor para la organización se determina de acuerdo a la siguiente escala economica 
   * Bajo    (B)     0<x349.999
   * Medio (M)    350.000<x<4.499.999
   * Alto    (A)     5.500.000<x< 50.000.000

Modificación; evalúa el impacto en los objetivos estratégicos de la organización cuando se modifica la información contenida en la base de datos, se determina de acuerdo a la siguiente escala 
   * Modificable       (M)    con un  Impacto Bajo
   * No Modificable  (NM) con un Impacto Alto
   
|TABLA|CAMPO|Tipo|Requisitos Legales|Criticidad|Divulgacion|Modificacion|Valor|
|-----|-----|----|------------------|----------|-----------|------------|-----|
|CONTRATOS|SUJETO DE CONTROL|Texto simple|N/A|NC|D |M |B|
|CONTRATOS|EVENTO|Texto simple|N/A|NC|D |M |B|
|CONTRATOS|TIPO DE REGISTRO|Texto simple|N/A|NC|D |M |B|
|CONTRATOS|CÓDIGO CONTRATO|Texto simple|N/A|NC|ND|NM|M|
|CONTRATOS|IDENTIFICACIÓN CONTRATISTA|Texto simple|N/A|C |D |M |B|
|CONTRATOS|NOMBRE CONTRATISTA|Texto simple|N/A|C |D |M |B|
|CONTRATOS|CÓDIGO DEL PROYECTO|Texto simple|N/A|NC|ND|NM|M|
|CONTRATOS|NOMBRE DEL PROYECTO|Texto simple|N/A|NC|ND|NM|M|
|CONTRATOS|SECTOR DEL PROYECTO|Texto simple|N/A|NC|D |M |B|
|CONTRATOS|VALOR DEL PROYECTO|Texto simple|1581|NC|ND|NM|A|
|CONTRATOS|VALOR EJECUTADO DEL PROYECTO|Texto simple|1581|NC|ND|NM|A|
|CONTRATOS|OBJETO DEL CONTRATO|Texto simple|N/A|NC|ND|NM|M|
|CONTRATOS|FECHA SUSCRIPCIÓN|Texto simple|N/A|NC|ND|NM|M|
|CONTRATOS|FECHA INICIO|Texto simple|N/A|NC|ND|NM|M|
|CONTRATOS|PLAZO ESTIMADO|Número|N/A|NC|ND|NM|M|
|CONTRATOS|VALOR CONTRATO|Texto simple|1581|NC|D |NM|A|
|CONTRATOS|PROCESO DE CONTRATACIÓN|Texto simple|N/A|NC|D |M |B|
|CONTRATOS|TIPOLOGÍA|Texto simple|N/A|NC|D |M |B|
|CONTRATOS|IDENTIFICACIÓN INTERVENTOR|Número|N/A|NC|D |NM|B|
|CONTRATOS|NOMBRE DEL INTERVENTOR|Texto simple|N/A|C |D |NM|B|
|CONTRATOS|TIPO INTERVENTOR|Texto simple|N/A|NC|D |M |B|
|CONTRATOS|No CONTRATO INTERVENTOR|Texto simple|N/A|NC|D |M |B|
|CONTRATOS|DISPONIBILIDADES PRESUPUESTALES|Texto simple|N/A|NC|D |M |A|
|CONTRATOS|REGISTROS PRESUPUESTALES|Número|N/A|NC|D |M |A|
|COTROL_ACCESO|IDENTIFICACIÓN CONTRATISTA|Texto simple|1581|C |D |NM|B|
|COTROL_ACCESO|HUELLA|Texto simple|1581|C |D |NM|B|
|DATOS_CONTRATISTAS|IDENTIFICACIÓN CONTRATISTA|Texto simple|1581|C |ND|NM|M|
|DATOS_CONTRATISTAS|DIRECCION CONTRATISTA|Texto simple|1581|C |ND|NM|M|
|DATOS_CONTRATISTAS|TELEFONO CONTRATISTA|Texto simple|1581|C |ND|NM|M|
|DATOS_CONTRATISTAS|CELULAR CONTRATISTA|Texto simple|1581|C |ND|NM|M|
|DATOS_CONTRATISTAS|CORREO CONTRATISTA|Texto simple|1581|C |ND|NM|M|
|DATOS_CONTRATISTAS|NOMBRE CONTRATISTA|Texto simple|1581|C |ND|NM|M|
|EMPLEADOS|NOMBRE|Texto simple|1581|NC|D |NM|B|
|EMPLEADOS|APELLIDO|Texto simple|1581|NC|D |NM|B|
|EMPLEADOS|TIPO DE DOCUMENTO|Texto simple|1581|NC|D |NM|B|
|EMPLEADOS|IDENTIFICACION|Texto simple|1581|C |D |NM|B|
|EMPLEADOS|FECHA DE NACIMIENTO|Texto simple|1581|C |D |NM|B|
|SALARIOS|SALARIO DEVENGADO|Texto simple|1581|C |ND|NM|M|
|SALARIOS|DEDUCCIONES|Texto simple|1581|C |ND|NM|M|
|SALARIOS|PRIMAS EXTRAS|Texto simple|1581|C |ND|NM|M|
|SALARIOS|BONO DE MOVILIDAD|Texto simple|1581|C |ND|NM|M|
|SALARIOS|COMISIONES|Texto simple|1581|C |ND|NM|M|
|SALARIOS|TIPO DE DOCUMENTO|Texto simple|1581|NC|D |NM|B|
|SALARIOS|IDENTIFICACION|Texto simple|1581|C |D |NM|B|
|SALARIOS|NOMBRE |Texto simple|1581|NC|D |NM|B|
|SALARIOS|APELLIDO|Texto simple|1581|NC|D |NM|B|

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
